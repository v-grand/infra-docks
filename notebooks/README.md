# Infrastructure Examples - Jupyter Notebooks

Добро пожаловать в коллекцию интерактивных туториалов по развертыванию инфраструктуры!

## 🎯 Комплексные End-to-End Туториалы

Эти ноутбуки демонстрируют полный цикл развертывания приложений с использованием всех модулей infra-*.

### 1. 🚀 [End-to-End Web Application Deployment](./end-to-end-webapp-deployment.ipynb)

**Уровень**: Intermediate  
**Время**: ~2 часа  
**Описание**: Полный туториал по развертыванию веб-приложения (Frontend + Backend + Database) от нуля до production.

**Что покрывается**:
- ✅ Создание проекта из `infra-template`
- ✅ Настройка сети с `infra-network` (VPC, Tailscale)
- ✅ Управление секретами с `infra-secrets` (SOPS)
- ✅ Развертывание в AWS (S3, ECS, RDS)
- ✅ CI/CD с `infra-ci` (GitHub Actions)
- ✅ Мониторинг с `infra-monitoring` (CloudWatch, Grafana)

**Архитектура**:
```
CloudFront → S3 (Frontend)
           → ALB → ECS Fargate (Backend) → RDS PostgreSQL
```

---

### 2. ☸️ [AWS Full Stack с Kubernetes (EKS)](./aws-k8s-fullstack.ipynb)

**Уровень**: Advanced  
**Время**: ~3 часа  
**Описание**: Развертывание микросервисного приложения на Amazon EKS с полным production stack.

**Что покрывается**:
- ✅ EKS кластер с node groups (on-demand + spot)
- ✅ Istio Service Mesh для управления трафиком
- ✅ ALB Ingress Controller
- ✅ ArgoCD для GitOps
- ✅ Prometheus + Grafana для мониторинга
- ✅ Horizontal Pod Autoscaler (HPA)
- ✅ Cluster Autoscaler

**Архитектура**:
```
Route53 → ALB Ingress → Istio Gateway
                      → Frontend Service
                      → API Gateway Service
                      → Microservices (Orders, Products)
                      → RDS + ElastiCache
```

---

### 3. 🌐 [Multi-Cloud Hybrid Infrastructure](./multicloud-hybrid-infrastructure.ipynb)

**Уровень**: Expert  
**Время**: ~4 часа  
**Описание**: Гибридное развертывание с использованием AWS + GCP + On-Premise через Tailscale mesh VPN.

**Что покрывается**:
- ✅ Multi-cloud Terraform setup (AWS + GCP)
- ✅ Tailscale Mesh VPN для связи между облаками
- ✅ AWS: Frontend, API Gateway, RDS
- ✅ GCP: BigQuery, Dataflow, Cloud Run (ML API)
- ✅ On-Premise: Legacy systems integration
- ✅ Cross-cloud data pipeline
- ✅ Unified monitoring (Prometheus)

**Архитектура**:
```
Tailscale Mesh VPN
    ├── AWS (Frontend, API, RDS)
    ├── GCP (BigQuery, ML API, Data Lake)
    └── On-Premise (Legacy DB, File Storage)
```

---

### 4. 🏭 [Production-Ready Infrastructure](./production-ready-infrastructure.ipynb)

**Уровень**: Expert  
**Время**: ~4 часа  
**Описание**: Полный production setup со всеми best practices для enterprise-grade приложений.

**Что покрывается**:
- ✅ High Availability (Multi-AZ, RDS Multi-AZ, Read Replicas)
- ✅ Security (WAF, Security Groups, KMS, Secrets Manager)
- ✅ Comprehensive Monitoring (CloudWatch, Container Insights)
- ✅ Backup & Disaster Recovery (AWS Backup)
- ✅ Auto-Scaling (ECS Service, RDS)
- ✅ CI/CD с security scanning
- ✅ Compliance (VPC Flow Logs, CloudTrail, Encryption)
- ✅ Cost Optimization

**Production Checklist**:
- SSL/TLS certificates (ACM)
- DNS (Route53)
- Monitoring alerts (SNS)
- Backup strategy
- Disaster recovery plan
- Security audit
- Load testing
- Operational runbook

---

## 📚 Базовые Туториалы

### [Terraform Demo](./terraform-demo.ipynb)
Введение в Terraform и Infrastructure as Code.

### [CI/CD Pipeline](./ci-cd-pipeline.ipynb)
Основы Continuous Integration и Continuous Deployment.

### [Infra-Core Usage](./infra-core-usage.ipynb)
Использование базовых модулей из infra-core.

### [Tailscale Mesh](./tailscale-mesh.ipynb)
Настройка Tailscale VPN для безопасного доступа.

---

## 🎓 Рекомендуемый путь обучения

### Для начинающих:
1. **Terraform Demo** - Основы IaC
2. **CI/CD Pipeline** - Автоматизация развертывания
3. **Infra-Core Usage** - Работа с модулями
4. **End-to-End Web Application** - Первое полное приложение

### Для опытных:
1. **End-to-End Web Application** - Освежить знания
2. **AWS K8s Full Stack** - Микросервисы и Kubernetes
3. **Production-Ready Infrastructure** - Best practices
4. **Multi-Cloud Hybrid** - Advanced архитектура

---

## 🛠️ Требования

### Обязательные инструменты:
- [Terraform](https://www.terraform.io/downloads) >= 1.5.0
- [AWS CLI](https://aws.amazon.com/cli/) >= 2.0
- [kubectl](https://kubernetes.io/docs/tasks/tools/) >= 1.28 (для K8s туториалов)
- [SOPS](https://github.com/mozilla/sops) >= 3.7 (для секретов)
- [Helm](https://helm.sh/docs/intro/install/) >= 3.0 (для K8s туториалов)

### Опциональные инструменты:
- [Tailscale](https://tailscale.com/download) (для VPN туториалов)
- [Docker](https://docs.docker.com/get-docker/) (для локальной разработки)
- [gcloud CLI](https://cloud.google.com/sdk/docs/install) (для GCP туториалов)

### Учетные записи:
- AWS Account с соответствующими правами
- GCP Account (для multi-cloud туториалов)
- GitHub Account (для CI/CD)
- Tailscale Account (для VPN туториалов)

---

## 📖 Как использовать ноутбуки

### Локально с Jupyter:

```bash
# Установка Jupyter
pip install jupyter

# Запуск Jupyter
cd notebooks
jupyter notebook
```

### В VS Code:

1. Установите расширение "Jupyter"
2. Откройте `.ipynb` файл
3. Выберите Python kernel
4. Запускайте ячейки по очереди

### В JupyterLab:

```bash
# Установка JupyterLab
pip install jupyterlab

# Запуск
jupyter lab
```

---

## ⚠️ Важные замечания

### Стоимость
Развертывание инфраструктуры из этих туториалов **будет стоить денег**. Убедитесь, что:
- Вы понимаете pricing модель AWS/GCP
- Настроены billing alerts
- Вы удаляете ресурсы после тестирования (`terraform destroy`)

### Безопасность
- **Никогда** не коммитьте реальные credentials в Git
- Используйте SOPS для шифрования секретов
- Следуйте принципу least privilege для IAM ролей
- Регулярно ротируйте credentials

### Best Practices
- Всегда используйте `terraform plan` перед `apply`
- Храните Terraform state в S3 с encryption
- Используйте DynamoDB для state locking
- Тегируйте все ресурсы для cost tracking

---

## 🤝 Вклад в проект

Нашли ошибку или хотите улучшить туториал?

1. Fork репозиторий
2. Создайте feature branch
3. Внесите изменения
4. Создайте Pull Request

---

## 📞 Поддержка

- 📧 Email: support@v-grand.com
- 💬 Slack: [v-grand workspace](https://v-grand.slack.com)
- 📚 Документация: [infra-docs.v-grand.com](https://infra-docs.v-grand.com)
- 🐛 Issues: [GitHub Issues](https://github.com/v-grand/infra-docs/issues)

---

## 📝 Лицензия

MIT License - см. [LICENSE](../LICENSE) файл для деталей.

---

## 🌟 Дополнительные ресурсы

### Официальная документация:
- [Terraform Documentation](https://www.terraform.io/docs)
- [AWS Documentation](https://docs.aws.amazon.com/)
- [Kubernetes Documentation](https://kubernetes.io/docs/)
- [Istio Documentation](https://istio.io/latest/docs/)

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

**Happy Infrastructure Coding! 🚀**
