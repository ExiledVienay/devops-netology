# devops-netology
*В файле гитигнор в каталоге терраформ указанны файлы которые будут проигнорированы в будущем при работе с терраформ. 
*В том числе файл логрования неисправностей. исключения и внутренние конфигурационные файлы в которые не надо вносит изменения:
1. Будут игнорироваться все файлы c расширением .tfstate; .tfvars; override.tf; verride.tf.json;
2. Каталог /.terraform/
3. Файлы логировани crash.log
4. Конфигурационные файлы .terraformrc и terraform.rc
