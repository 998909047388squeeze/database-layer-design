# Database Layer Design

## Architectural Pattern

MVC (Model–View–Controller)

## Entities

### USER — Key Entity
- user_id — Primary Key
- full_name
- email
- phone_numbers — Multivalued Attribute

### MOVIE — Key Entity
- movie_id — Primary Key
- title
- release_year
- duration_minutes
- age_rating

### GENRE — Key Entity
- genre_id — Primary Key
- genre_name
- description

### WATCH_HISTORY — Weak Entity
- user_id — Primary Key, Foreign Key
- history_number — Weak/Partial Key
- movie_id — Foreign Key
- started_at
- ended_at
- watch_duration — Derived Attribute

### MOVIE_GENRE — Associative Entity
- movie_id — Primary Key, Foreign Key
- genre_id — Primary Key, Foreign Key
- assigned_at

## Relationships

1. USER → WATCH_HISTORY
   - Cardinality: 1 : 0..N
   - Identifying relationship

2. MOVIE → WATCH_HISTORY
   - Cardinality: 1 : 0..N

3. MOVIE → MOVIE_GENRE
   - Cardinality: 1 : 0..N

4. GENRE → MOVIE_GENRE
   - Cardinality: 1 : 0..N

## Entity Types

- USER — Key Entity
- MOVIE — Key Entity
- GENRE — Key Entity
- WATCH_HISTORY — Weak Entity
- MOVIE_GENRE — Associative Entity

## Special Attributes

- phone_numbers — Multivalued Attribute
- history_number — Weak/Partial Key
- watch_duration — Derived Attribute
