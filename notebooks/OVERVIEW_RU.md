# Комплексные примеры развертывания

## 🎯 Обзор

В этом разделе представлены подробные сквозные примеры (end-to-end case studies), демонстрирующие полный цикл развертывания различных типов приложений с использованием всех модулей инфраструктуры v-grand.

Каждый туториал представлен в формате интерактивного Jupyter notebook, что позволяет запускать код пошагово и сразу видеть результаты.

---

## 📚 Доступные туториалы

### 🚀 1. Развертывание веб-приложения (End-to-End)

**Файл**: [`end-to-end-webapp-deployment.ipynb`](./end-to-end-webapp-deployment.ipynb)  
**Уровень**: Средний  
**Продолжительность**: ~2 часа

#### Что вы изучите:

Полный цикл развертывания типичного веб-приложения (React Frontend + FastAPI Backend + PostgreSQL Database) с нуля до production.

#### Охватываемые темы:

1. **Создание проекта** из `infra-template`
2. **Настройка сети** (VPC, подсети, Tailscale VPN) через `infra-network`
3. **Управление секретами** с помощью SOPS (`infra-secrets`)
4. **Развертывание в AWS**:
   - S3 + CloudFront для фронтенда
   - ECS Fargate для бэкенда
   - RDS PostgreSQL для базы данных
5. **Настройка CI/CD** через GitHub Actions (`infra-ci`)
6. **Мониторинг** с CloudWatch и Grafana (`infra-monitoring`)

#### Архитектура:

```
CloudFront (CDN)
    ↓
S3 Bucket (React Frontend)
    ↓
Application Load Balancer
    ↓
ECS Fargate (FastAPI Backend)
    ↓
RDS PostgreSQL (Database)
```

---

### ☸️ 2. Микросервисы на Kubernetes (AWS EKS)

**Файл**: [`aws-k8s-fullstack.ipynb`](./aws-k8s-fullstack.ipynb)  
**Уровень**: Продвинутый  
**Продолжительность**: ~3 часа

#### Что вы изучите:

Развертывание полноценного микросервисного приложения на Amazon EKS с использованием современных инструментов оркестрации и управления.

#### Охватываемые темы:

1. **Создание EKS кластера** с node groups (on-demand + spot instances)
2. **Установка Istio Service Mesh** для управления трафиком
3. **Настройка ALB Ingress Controller**
4. **Развертывание микросервисов** (Frontend, API Gateway, Orders, Products)
5. **GitOps с ArgoCD** для автоматического развертывания
6. **Мониторинг** с Prometheus и Grafana
7. **Автоскейлинг** (HPA для подов, Cluster Autoscaler для нод)

#### Архитектура:

```
Route53 (DNS)
    ↓
ALB Ingress Controller
    ↓
Istio Gateway
    ├── Frontend Service
    ├── API Gateway Service
    ├── Auth Service
    ├── Orders Service
    └── Products Service
         ↓
    RDS + ElastiCache
```

---

### 🌐 3. Гибридная мульти-облачная инфраструктура

**Файл**: [`multicloud-hybrid-infrastructure.ipynb`](./multicloud-hybrid-infrastructure.ipynb)  
**Уровень**: Эксперт  
**Продолжительность**: ~4 часа

#### Что вы изучите:

Создание гибридной инфраструктуры, объединяющей AWS, GCP и on-premise системы через Tailscale mesh VPN.

#### Охватываемые темы:

1. **Multi-cloud Terraform setup** для управления AWS и GCP
2. **Tailscale Mesh VPN** для безопасной связи между облаками
3. **AWS компоненты**:
   - Frontend (S3 + CloudFront)
   - API Gateway (ECS)
   - Database (RDS)
4. **GCP компоненты**:
   - Data Lake (Cloud Storage)
   - Analytics (BigQuery)
   - ML API (Cloud Run)
   - Data Processing (Dataflow)
5. **On-Premise интеграция** с legacy системами
6. **Cross-cloud data pipeline** для синхронизации данных
7. **Unified monitoring** с Prometheus

#### Архитектура:

```
Tailscale Mesh VPN
    ├── AWS (Frontend, API Gateway, RDS)
    ├── GCP (BigQuery, ML API, Data Lake)
    └── On-Premise (Legacy DB, File Storage)
```

---

### 🏭 4. Production-Ready инфраструктура

**Файл**: [`production-ready-infrastructure.ipynb`](./production-ready-infrastructure.ipynb)  
**Уровень**: Эксперт  
**Продолжительность**: ~4 часа

#### Что вы изучите:

Создание enterprise-grade инфраструктуры со всеми необходимыми компонентами для production окружения.

#### Охватываемые темы:

1. **High Availability**:
   - Multi-AZ deployment
   - RDS Multi-AZ с read replicas
   - NAT Gateway в каждой AZ
2. **Security**:
   - AWS WAF для защиты от атак
   - Security Groups и NACLs
   - KMS для шифрования
   - AWS Secrets Manager
3. **Monitoring & Observability**:
   - CloudWatch Dashboards
   - Container Insights
   - Performance Insights для RDS
   - Алармы и уведомления (SNS)
4. **Backup & Disaster Recovery**:
   - AWS Backup с автоматическими бэкапами
   - Retention policies (daily, weekly, monthly)
   - Cross-region replication
5. **Auto-Scaling**:
   - ECS Service auto-scaling
   - Target tracking policies
6. **CI/CD**:
   - GitHub Actions с security scanning
   - Blue-Green deployments
   - Automated rollbacks
7. **Compliance**:
   - VPC Flow Logs
   - CloudTrail для аудита
   - Encryption at rest и in transit

#### Production Checklist:

- ✅ SSL/TLS certificates (ACM)
- ✅ DNS configuration (Route53)
- ✅ Monitoring alerts
- ✅ Backup strategy
- ✅ Disaster recovery plan
- ✅ Security audit
- ✅ Load testing
- ✅ Operational runbook

---

## 🎓 Рекомендуемый путь обучения

### Для начинающих:

1. **Terraform Demo** - Основы Infrastructure as Code
2. **CI/CD Pipeline** - Автоматизация развертывания
3. **Infra-Core Usage** - Работа с базовыми модулями
4. **End-to-End Web Application** - Первое полное приложение

### Для опытных разработчиков:

1. **End-to-End Web Application** - Освежить знания
2. **AWS K8s Full Stack** - Микросервисы и Kubernetes
3. **Production-Ready Infrastructure** - Best practices
4. **Multi-Cloud Hybrid** - Advanced архитектура

---

## 🛠️ Требования

### Обязательные инструменты:

- [Terraform](https://www.terraform.io/downloads) >= 1.5.0
- [AWS CLI](https://aws.amazon.com/cli/) >= 2.0
- [Python](https://www.python.org/downloads/) >= 3.9
- [Jupyter](https://jupyter.org/install) для запуска ноутбуков

### Для Kubernetes туториалов:

- [kubectl](https://kubernetes.io/docs/tasks/tools/) >= 1.28
- [Helm](https://helm.sh/docs/intro/install/) >= 3.0
- [istioctl](https://istio.io/latest/docs/setup/getting-started/) >= 1.19

### Для работы с секретами:

- [SOPS](https://github.com/mozilla/sops) >= 3.7
- [age](https://github.com/FiloSottile/age) или AWS KMS

### Для Multi-Cloud:

- [gcloud CLI](https://cloud.google.com/sdk/docs/install) для GCP
- [Tailscale](https://tailscale.com/download) для VPN

### Учетные записи:

- **AWS Account** с соответствующими IAM правами
- **GCP Account** (для multi-cloud туториалов)
- **GitHub Account** (для CI/CD)
- **Tailscale Account** (для VPN туториалов)

---

## 📖 Как использовать ноутбуки

### Вариант 1: Локально с Jupyter

```bash
# Установка Jupyter
pip install jupyter notebook

# Переход в директорию с ноутбуками
cd notebooks

# Запуск Jupyter
jupyter notebook
```

### Вариант 2: В VS Code

1. Установите расширение **"Jupyter"** в VS Code
2. Откройте `.ipynb` файл
3. Выберите Python kernel
4. Запускайте ячейки последовательно (Shift+Enter)

### Вариант 3: JupyterLab

```bash
# Установка JupyterLab
pip install jupyterlab

# Запуск
jupyter lab
```

---

## ⚠️ Важные замечания

### 💰 Стоимость

Развертывание инфраструктуры из этих туториалов **будет стоить денег**. 

**Рекомендации**:
- Изучите [AWS Pricing Calculator](https://calculator.aws.amazon.com/)
- Настройте [AWS Billing Alerts](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/monitor_estimated_charges_with_cloudwatch.html)
- Используйте `terraform destroy` после тестирования
- Рассмотрите использование [AWS Free Tier](https://aws.amazon.com/free/)

### 🔒 Безопасность

**Критически важно**:
- ❌ **Никогда** не коммитьте реальные credentials в Git
- ✅ Используйте SOPS для шифрования секретов
- ✅ Следуйте принципу least privilege для IAM ролей
- ✅ Регулярно ротируйте credentials
- ✅ Добавьте `terraform.tfvars` и `secrets.yaml` в `.gitignore`

### 📋 Best Practices

- ✅ Всегда используйте `terraform plan` перед `apply`
- ✅ Храните Terraform state в S3 с encryption
- ✅ Используйте DynamoDB для state locking
- ✅ Тегируйте все ресурсы для cost tracking
- ✅ Используйте workspaces для разных окружений
- ✅ Документируйте все изменения

---

## 📊 Статистика туториалов

| Метрика | Значение |
|---------|----------|
| Всего ноутбуков | 8 |
| Комплексных case studies | 4 |
| Базовых туториалов | 4 |
| Общее время изучения | 13+ часов |
| Покрытых модулей infra-* | 8 (все) |
| Строк кода | 2000+ |
| Облачных провайдеров | 2 (AWS, GCP) |

---

## 🌟 Дополнительные ресурсы

### Официальная документация:

- [Terraform Documentation](https://www.terraform.io/docs)
- [AWS Documentation](https://docs.aws.amazon.com/)
- [Kubernetes Documentation](https://kubernetes.io/docs/)
- [Istio Documentation](https://istio.io/latest/docs/)
- [ArgoCD Documentation](https://argo-cd.readthedocs.io/)

### Наши репозитории:

- [infra-template](https://github.com/v-grand/infra-template) - Шаблоны проектов
- [infra-core](https://github.com/v-grand/infra-core) - Базовые модули
- [infra-aws](https://github.com/v-grand/infra-aws) - AWS модули
- [infra-gcp](https://github.com/v-grand/infra-gcp) - GCP модули
- [infra-k8s](https://github.com/v-grand/infra-k8s) - Kubernetes модули
- [infra-network](https://github.com/v-grand/infra-network) - Сетевые модули
- [infra-secrets](https://github.com/v-grand/infra-secrets) - Управление секретами
- [infra-ci](https://github.com/v-grand/infra-ci) - CI/CD workflows
- [infra-monitoring](https://github.com/v-grand/infra-monitoring) - Мониторинг

---

## 🤝 Вклад в проект

Нашли ошибку или хотите улучшить туториал?

1. Fork репозиторий [infra-docs](https://github.com/v-grand/infra-docs)
2. Создайте feature branch (`git checkout -b feature/improve-tutorial`)
3. Внесите изменения
4. Commit изменения (`git commit -am 'Улучшен туториал X'`)
5. Push в branch (`git push origin feature/improve-tutorial`)
6. Создайте Pull Request

---

## 📞 Поддержка

Нужна помощь? Свяжитесь с нами:

- 📧 **Email**: support@v-grand.com
- 💬 **Slack**: [v-grand workspace](https://v-grand.slack.com)
- 📚 **Документация**: [infra-docs.v-grand.com](https://infra-docs.v-grand.com)
- 🐛 **Issues**: [GitHub Issues](https://github.com/v-grand/infra-docs/issues)
- 💡 **Discussions**: [GitHub Discussions](https://github.com/v-grand/infra-docs/discussions)

---

## 📝 Лицензия

MIT License - см. [LICENSE](../LICENSE) файл для деталей.

---

**Успешного изучения! 🚀**

*Эти туториалы созданы с ❤️ командой v-grand для сообщества DevOps и Cloud Engineers.*
