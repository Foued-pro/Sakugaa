# Sakugaa – Jour 1

## Base de données (via Supabase)

Mise en place d’un schéma pour gérer les vidéos, leurs auteurs et leurs tags.

### Tables créées :

#### 1. `videos`  
- `id` (clé primaire)  
- `author_id` (clé étrangère → `authors.id`)  
- `video_url` (chaîne de caractères, URL de la vidéo)  
- `created_at` (timestamp, généré automatiquement par Supabase)

#### 2. `authors`  
- `id` (clé primaire)  
- `name` (nom de l’auteur)

#### 3. `tags`  
- `id` (clé primaire)  
- `name` (nom du tag)

#### 4. `video_tags`  
Table de liaison qui associe plusieurs tags à une vidéo (relation many-to-many).  
- `video_id` (clé étrangère → `videos.id`)  
- `tag_id` (clé étrangère → `tags.id`)  
- **Clé primaire composite `(video_id, tag_id)` garantissant l’unicité de chaque lien vidéo-tag**

---

Ce schéma permet :  
- Une relation **1-N** entre `authors` et `videos`.  
- Une relation **N-N** entre `videos` et `tags` via la table de liaison `video_tags`.
