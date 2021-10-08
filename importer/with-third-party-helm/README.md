# Third Party Helm + Importer

Helm Chart management using `values-[env].yaml` for envirnomental difference could lead to duplicated seutp.

In this directory, the basic configuration is in `values-template.yaml`, and each env can either pull in from the template, or have specific setup for their requirements.

- `prod.yaml` is basically a copy of `values-template.yaml`
- `qa.yaml` and `staging.yaml` are slightly different from `prod.yaml`, but they share the same exact spec. If the template file is updated, both environments will be affected. If one environment is updated, you would see the file change only in the affected file.
- `dev.yaml` is also slightly different from `qa.yaml`, but uses a bulk of the same configuration as it pulls from `values-template.yaml`

## Template and Generated Files

`prod.yaml`, `staging.yaml`, `qa.yaml`, and `dev.yaml` are all template files, and they have a special marker `== importer-skip-update ==`. This means running `importer update` on those files would not actually update the file in place. This means these files are only used as a template, and you can use these files as a source file for `importer generate`.

This example uses these files with the following command:

```bash
d=(prod qa staging dev); for i in "${d[@]}"; do importer generate importer/with-helm/$i.yaml -o importer/with-helm/grafana/values-$i.gen.yaml; done
```

When the actual values.yaml file is lengthy, it can be cumbersome to check the difference for each file. So, insetad of checking each `importer generate` results, the template files can be used for the review.
