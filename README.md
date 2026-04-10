# Hello World - PR to Linear Integration

## Opis

Automatyczna integracja między Pull Requests na GitHub a ticketami w Linear:
- Automatyczne dodawanie linku do PR w opisie Linear issue
- Dodawanie komentarzy o statusie PR (opened/merged/closed)
- Automatyczne wykrywanie ID Linear issue z tytułu PR

## Wymagania

1. **Linear API Key** - utwórz w [Linear API Settings](https://linear.app/settings/api)
2. **Linear Team ID** - ID zespołu w Linear (np. `team_xxx`)
3. **GitHub Secrets** - skonfiguruj w ustawieniach repozytorium:
   - `LINEAR_API_KEY` - twój Linear API key
   - `LINEAR_TEAM_ID` - ID zespołu

## Konfiguracja

### 1. Dodaj secrets do repozytorium

Przejdź do: `Settings > Secrets and variables > Actions`

Dodaj:
- `LINEAR_API_KEY` - klucz API Linear
- `LINEAR_TEAM_ID` - ID zespołu Linear

### 2. Skonfiguruj Linear API

Upewnij się, że masz uprawnienia do:
- Aktualizacji issue
- Dodawania komentarzy

## Format tytułów PR

Workflow automatycznie wykrywa ID Linear issue z tytułu PR:
- `PROJ-123: Opis zmian` → wykrywa `PROJ-123`
- `[PROJ-456] Feature: Nowa funkcja` → wykrywa `PROJ-456`

## Workflows

- `update-linear-on-pr.yml` - Główny workflow automatyzujący integrację

## Testowanie

Utwórz PR z tytułem zawierającym ID Linear issue (np. `TEST-1: Test PR`) aby sprawdzić integrację.

---

## Quick Setup (EN)

This project demonstrates GitHub → Linear PR integration. To set up:

1. Create a Linear API key at https://linear.app/settings/api
2. Add `LINEAR_API_KEY` secret to GitHub repo settings
3. Create PRs with Linear issue IDs in titles (e.g., `PROJ-123: My changes`)