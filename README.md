
# Supply & Demand - AIX

Entorno limpio generado para la Business Unit **AIX**.

## Pasos de despliegue

1. Crear un proyecto nuevo en Supabase.
2. Ejecutar el fichero `schema_aix.sql` en SQL Editor.
3. Crear usuarios en Authentication > Users.
4. Recuperar los UUID de usuarios:

```sql
select id, email from auth.users;
```

5. Insertar roles:

```sql
insert into public.user_roles (user_id, role)
values
  ('UUID_DEL_ADMIN', 'admin'),
  ('UUID_DEL_EDITOR', 'editor'),
  ('UUID_DEL_LECTOR', 'reader');
```

6. Editar en `index.html` y `dashboard.html`:

```javascript
const SUPABASE_URL = "https://xxxxx.supabase.co";
const SUPABASE_ANON_KEY = "xxxxx";
```

7. Subir `index.html` y `dashboard.html` al repo de GitHub.
8. Activar GitHub Pages.

## Roles

| Rol | Lectura | Alta/edición | Borrado |
|---|---:|---:|---:|
| reader | Sí | No | No |
| editor | Sí | Sí | No |
| admin | Sí | Sí | Sí |

## Nota

El entorno no incluye datos de ejemplo.
