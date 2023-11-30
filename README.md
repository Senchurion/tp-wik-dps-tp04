# Kubernetes Deployment avec Minikube

Ce projet démontre comment déployer des applications en utilisant Kubernetes sur Minikube. Il couvre la création d'un Pod simple, le remplacement de ce Pod par un ReplicaSet, puis par un Deployment, et la mise en place d'un Service et d'un Ingress pour l'accès externe.

## Prérequis

- [Minikube](https://minikube.sigs.k8s.io/docs/start/)
- [Kubectl](https://kubernetes.io/docs/tasks/tools/)

## Démarrage de Minikube

Avant de commencer, assurez-vous que Minikube est en cours d'exécution :

```bash
minikube start
```

## Déploiement d'un Pod

1. **Pod YAML** : Créez un fichier `pod.yaml` avec la spécification du Pod.
2. **Déployer le Pod** : Exécutez `kubectl apply -f pod.yaml`.

## Mise à Jour vers un ReplicaSet

1. **ReplicaSet YAML** : Remplacez le Pod par un ReplicaSet dans un fichier `replicaset.yaml`.
2. **Déployer le ReplicaSet** : Exécutez `kubectl apply -f replicaset.yaml`.

## Mise à Jour vers un Deployment

1. **Deployment YAML** : Créez un fichier `deployment.yaml` pour le Deployment avec une stratégie de mise à jour RollingUpdate.
2. **Déployer le Deployment** : Exécutez `kubectl apply -f deployment.yaml`.

## Création d'un Service

1. **Service YAML** : Créez un fichier `service.yaml` pour exposer le Deployment.
2. **Déployer le Service** : Exécutez `kubectl apply -f service.yaml`.
3. **Port Forwarding** : Utilisez `kubectl port-forward` pour tester le Service localement.

## Configuration d'Ingress avec Nginx

1. **Activer Ingress Nginx** : Exécutez `minikube addons enable ingress`.
2. **Ingress YAML** : Créez un fichier `ingress.yaml` pour configurer l'Ingress.
3. **Déployer l'Ingress** : Exécutez `kubectl apply -f ingress.yaml`.
4. **Mise à jour de `/etc/hosts`** : Ajoutez le nom de domaine de l'Ingress à votre fichier `/etc/hosts`.

## Accès via le Navigateur

Après la configuration de l'Ingress, vous pouvez accéder au service via le nom de domaine configuré dans votre navigateur.

## Nettoyage

Pour supprimer toutes les ressources créées, exécutez les commandes `kubectl delete` pour chaque fichier YAML utilisé.
