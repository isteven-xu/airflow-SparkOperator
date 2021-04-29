# Description

Airflow SparkOperator with customer submit comand and yarn cluster log monitor.

# Installation

Copy spark_submit_hook.py to airflow install path, eg: /site-packages/airflow/contrib/hooks Copy
spark_submit_operator.py to airflow install path, eg: /site-packages/airflow/contrib/operators

# Usage

```python
SparkSubmitOperator(
    task_id="task1",
    cmd="your spark submit command",
    dag="you DAG",
    on_failure_callback=None,
    on_success_callback=None
)

```

# How to get logs from airflow

If you submit spark with client, you can get logs easily, but if you submit spark with cluster , you can get logs from
SparkHistoryServer Or YarnHistoryServer rest api. Hers is for YarnHistoryServer,we get logs-page-url and pars the HTML
then print the logs .