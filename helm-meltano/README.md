# Helm Charts for use with Meltano

## Deploying Meltano UI

```bash
helm install -f meltano-ui/values.yaml meltano-ui ./meltano-ui
```

## Deploying Airflow

```bash
helm install -f airflow/values.yaml airflow ./airflow
```

