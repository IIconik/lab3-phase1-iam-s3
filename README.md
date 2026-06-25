# Lab 3 — IAM et S3

> Gestion des identités et accès AWS, stockage objet S3 et hébergement de site statique.
> Troisième lab de la **Phase 1 — AWS Fondamentaux**.

[![AWS](https://img.shields.io/badge/AWS-IAM%20%2B%20S3-FF9900?logo=amazonaws&logoColor=white)]()
[![Status](https://img.shields.io/badge/Status-Validated-3FB950)]()

---

## 🎯 Objectif

Comprendre IAM (identités et permissions), créer un bucket S3 public pour héberger un site statique, et attacher un rôle IAM à une instance EC2 pour qu'elle accède à S3 sans clés.

## 🏗️ Ce qui a été créé

| Ressource | Nom | Configuration |
|-----------|-----|---------------|
| **Bucket S3** | lab3-phase1-nathan-2701 | Website hosting activé |
| **Bucket Policy** | — | Allow s3:GetObject pour * |
| **Rôle IAM** | role-ec2-s3-lab-phase1 | AmazonS3ReadOnlyAccess |

## 🌐 Site statique S3

URL : `http://lab3-phase1-nathan-2701.s3-website.eu-west-3.amazonaws.com`

## 🔐 Bucket Policy appliquée

```json
{
    "Version": "2012-10-17",
    "Statement": [{
        "Effect": "Allow",
        "Principal": "*",
        "Action": "s3:GetObject",
        "Resource": "arn:aws:s3:::lab3-phase1-nathan-2701/*"
    }]
}
```

## 📄 Procédure

📄 **[Lab3_Phase1_IAM_S3.pdf](./Lab3_Phase1_IAM_S3.pdf)**

## ✅ Validation

- [x] Bucket S3 créé avec Block Public Access partiellement désactivé
- [x] Fichier index.html uploadé
- [x] Bucket policy permettant l'accès public en lecture
- [x] Site statique accessible depuis le navigateur
- [x] Rôle IAM créé avec AmazonS3ReadOnlyAccess
- [x] Rôle attaché à l'instance EC2
- [x] `aws s3 ls s3://lab3-phase1-nathan-2701` fonctionne sans clé

## 🎓 Compétences mises en pratique

- IAM : Users, Groups, Roles, Policies
- Structure d'une policy JSON (Effect, Action, Resource, Principal)
- Règle Deny > Allow
- S3 : buckets, objets, bucket policies
- Rôles IAM pour les services AWS (sans clés statiques)
- Static Website Hosting sur S3

---

**Parcours :** BTS SIO SISR → Bachelor ESGI Cloud/Réseaux → Mastère
**Objectif :** Cloud Infrastructure / Platform Engineer
