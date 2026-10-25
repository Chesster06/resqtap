# Database Schemas & Migrations

This directory contains the relational database schemas and SQL migration scripts for the ResQTap Supabase backend (PostgreSQL 15).

## Migration Order

1. **Primary Schema (`database/migrations/supabase_schema.sql`)**:
   - Enables PostGIS spatial extension.
   - Creates core tables: `profiles`, `medical_cards`, `reports`, `rooms`, `room_members`.
   - Configures primary Row Level Security (RLS) policies.

2. **Auxiliary Tables (`database/migrations/supabase_additional_tables.sql`)**:
   - Creates auxiliary tables: `highlights`, `user_notifications`, `room_tombstones`, `system_calls`, `system_metadata`, `registered_emails`.
   - Configures hardened RLS policies for public highlights and administrative metadata.

## Execution

Copy and execute each SQL migration script in sequence via the Supabase Dashboard SQL Editor:
1. Navigate to your Supabase project dashboard.
2. Select SQL Editor from the navigation menu.
3. Paste the contents of `supabase_schema.sql` and click Run.
4. Paste the contents of `supabase_additional_tables.sql` and click Run.
