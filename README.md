# Infrastructure scalable sous docker

Dans le cadre d'un cours de **devops** à l'IPI, je devais mettre en place une infrastructure **Docker** contenant un CMS.

Le cahier des charges de l'infrastructure est le suivant:

- Scalable
- Sécurisée
- Utilisation de TLS
- Persistence des données

```mermaid
graph TD
    A[Client] -->|443/80| C{Docker}
    C --> D[Bridge 1]
    D --> |443/80| E(Reverse proxy Nginx)
    E --> F[Bridge 2]
    G(WordPress) --> F[Bridge 2] 
    G --> H[Bridge 3]
    I(DB) --> H
```