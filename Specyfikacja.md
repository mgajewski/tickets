# Dokumentacja Aplikacji Mobilnej

## Spis Treści
- [Dokumentacja Aplikacji Mobilnej](#dokumentacja-aplikacji-mobilnej)
  - [Spis Treści](#spis-treści)
  - [Ekrany aplikacji](#ekrany-aplikacji)
    - [Ekran logowania](#ekran-logowania)
    - [Ekran rejestracji](#ekran-rejestracji)
    - [Strona główna](#strona-główna)
  - [Backend / API](#backend--api)
    - [Autoryzacja](#autoryzacja)
      - [`POST /api/auth/login`](#post-apiauthlogin)
      - [`POST /api/auth/register`](#post-apiauthregister)
    - [Zarządzanie użytkownikiem](#zarządzanie-użytkownikiem)
      - [`GET /api/user/me`](#get-apiuserme)
    - [Dane aplikacji](#dane-aplikacji)
      - [`GET /api/data/items`](#get-apidataitems)
  - [Uwagi końcowe](#uwagi-końcowe)

---

## Ekrany aplikacji

### Ekran logowania
- **Nazwa:** LoginScreen
- **Opis:** Ekran umożliwiający zalogowanie użytkownika do aplikacji.
- **Elementy UI:**
  - Pole e-mail
  - Pole hasło
  - Przycisk "Zaloguj"
  - Link do odzyskiwania hasła
- **Nawigacja:**
  - Po zalogowaniu: przejście do `Strona główna`
  - Link do: `Ekran rejestracji`
- **Uwagi specjalne:**
  - Walidacja adresu e-mail i hasła
  - Obsługa błędów logowania

### Ekran rejestracji
- **Nazwa:** RegisterScreen
- **Opis:** Formularz do rejestracji nowego użytkownika.
- **Elementy UI:**
  - Imię
  - Nazwisko
  - E-mail
  - Hasło
  - Powtórz hasło
  - Przycisk "Zarejestruj się"
- **Nawigacja:**
  - Po sukcesie: przejście do `Strona główna`
- **Uwagi specjalne:**
  - Sprawdzenie zgodności haseł
  - Obsługa błędów serwera

### Strona główna
- **Nazwa:** HomeScreen
- **Opis:** Główny ekran z dostępem do funkcjonalności aplikacji.
- **Elementy UI:**
  - Menu dolne (tab bar)
  - Lista danych / widżetów
- **Nawigacja:**
  - Dostęp do ekranów funkcjonalnych (np. Profil, Ustawienia)
- **Uwagi specjalne:**
  - Wczytywanie danych z backendu

<!-- Dodawaj kolejne ekrany zgodnie z powyższym schematem -->

---

## Backend / API

### Autoryzacja

#### `POST /api/auth/login`
- **Opis:** Logowanie użytkownika.
- **Parametry:**
  - `email`: string
  - `password`: string
- **Odpowiedź:**
  - `200 OK`: token JWT, dane użytkownika
  - `401 Unauthorized`: błędne dane logowania

#### `POST /api/auth/register`
- **Opis:** Rejestracja nowego użytkownika.
- **Parametry:**
  - `firstName`, `lastName`, `email`, `password`
- **Odpowiedź:**
  - `201 Created`: token JWT, dane użytkownika
  - `400 Bad Request`: walidacja

### Zarządzanie użytkownikiem

#### `GET /api/user/me`
- **Opis:** Pobranie danych aktualnie zalogowanego użytkownika.
- **Wymaga autoryzacji:** ✅

### Dane aplikacji

#### `GET /api/data/items`
- **Opis:** Pobranie listy danych do wyświetlenia na stronie głównej.
- **Parametry opcjonalne:** np. `filter`, `sort`
- **Odpowiedź:**
  - `200 OK`: lista obiektów danych

<!-- Dodawaj kolejne endpointy zgodnie z powyższym schematem -->

---

## Uwagi końcowe
- Dokument będzie aktualizowany w miarę postępu prac nad aplikacją.
- Wszelkie zmiany w API powinny być odnotowywane tutaj.
