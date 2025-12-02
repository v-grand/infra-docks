# infra-core

Kompleksowa biblioteka modułów Terraform wielokrotnego użytku, przeznaczona do zarządzania infrastrukturą wielochmurową. Biblioteka ta obsługuje AWS, GCP, Hetzner i Contabo, umożliwiając elastyczne i niezależne od platformy wdrażanie infrastruktury.

## 🚀 Funkcje

- **Wsparcie dla wielu chmur**: Bezproblemowe przydzielanie zasobów u głównych dostawców chmurowych.
- **Modułowa konstrukcja**: Komponenty wielokrotnego użytku dla maszyn wirtualnych, VPC, baz danych i innych.
- **Najlepsze praktyki**: Zbudowane z myślą o bezpieczeństwie i skalowalności.
- **Integracja z Tailscale**: Łatwa konfiguracja bezpiecznej sieci kratowej.

## 📦 Moduły

| Moduł | Opis | Obsługiwani dostawcy |
| :--- | :--- | :--- |
| `vm` | Tworzenie maszyn wirtualnych (EC2, GCE) | AWS, GCP |
| `vpc` | Konfiguracja sieci (VPC, podsieci) | AWS, GCP |
| `db` | Zarządzane bazy danych (RDS, Cloud SQL) | AWS, GCP |
| `tailscale` | Sieć kratowa Tailscale | Wszyscy |
| `k8s` | Klastry Kubernetes (EKS, GKE) | AWS, GCP |

## 🛠️ Wymagania wstępne

- [Terraform](https://www.terraform.io/downloads) >= 1.0
- Poświadczenia dostawcy chmury (skonfigurowane za pomocą zmiennych środowiskowych lub CLI)

## 📖 Użycie

Oto podstawowy przykład użycia modułu `vm` w konfiguracji Terraform:

```hcl
module "my_web_server" {
  source        = "./modules/vm" # Lub źródło z git
  provider      = "aws"
  instance_type = "t3.micro"
  ami           = "ami-0c55b159cbfafe1f0"
  tags = {
    Environment = "dev"
  }
}
```
