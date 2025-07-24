# Sakugaa – Jour 1

## Base de données (via Supabase)

Mise en place d’un schéma relationnel simple pour gérer les vidéos, leurs auteurs, et leurs tags.

### Tables créées :

#### 1. `videos`
- `id` (primary key)
- `author_id` (foreign key → `authors.id`)
- `video_url` (string, URL vers la vidéo)
- `created_at` (timestamp, généré automatiquement par Supabase)

#### 2. `authors`
- `id` (primary key)
- `name` (nom de l’auteur)

#### 3. `tags`
- `id` (primary key)
- `name` (nom du tag)

#### 4. `video_tags`
Table de jointure permettant d’associer plusieurs tags à une vidéo.
- `video_id` (foreign key → `videos.id`)
- `tag_id` (foreign key → `tags.id`)

---

Ce schéma permet :
- Une relation **1-N** entre `authors` et `videos`.
- Une relation **N-N** entre `videos` et `tags`, via la table `video_tags`.
