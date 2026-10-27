# Abuja Jobs Tracker - Built with Supabase

A simple, open-source job application tracker for developers in Abuja applying to remote companies. Built to learn the Supabase stack.

**Live Demo:** Coming soon  
**Built by:** jafarelone903 - Abuja, Nigeria (open to remote)

### Why I Built This
After exploring Supabase docs (Auth, Postgres, RLS), I wanted to build something practical that solves my own problem: tracking remote applications.

### Tech Stack
- **Supabase Auth** - Email auth for secure login
- **PostgreSQL** - Jobs table with RLS policies
- **Supabase Realtime** - Instant status updates
- **Next.js 14** - Frontend
- **Row Level Security** - Users only see their own jobs

### Schema
```sql
create table jobs (
  id uuid primary key default gen_random_uuid(),
  user_id uuid references auth.users,
  company text,
  status text,
  date_applied date,
  notes text
);
