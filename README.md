# Todo API – Spring Boot

## Opis projektu

Todo API to prosta aplikacja backendowa napisana w Spring Boot, która umożliwia zarządzanie listą zadań (Todo). Aplikacja udostępnia REST API pozwalające na tworzenie, odczyt, aktualizację i usuwanie zadań oraz oznaczanie ich jako wykonanych. Dane przechowywane są w bazie H2.

## Jak uruchomić aplikację

### IntelliJ IDEA

1. Otwórz projekt w IntelliJ IDEA.
2. Uruchom klasę `TodoApiApplication`.

### Terminal (Windows)

Uruchom aplikację poleceniem:

```bash
.\mvnw spring-boot:run
```

Po uruchomieniu aplikacja będzie dostępna pod adresem:

```text
http://localhost:8080
```

> Jeżeli port `8080` jest zajęty, można zmienić go w pliku `application.properties`, dodając np.:
>
> ```properties
> server.port=8081
> ```

## Dostępne endpointy

| Metoda HTTP | URL                        | Opis                                               |
| ----------- | -------------------------- | -------------------------------------------------- |
| GET         | `/api/tasks`               | Pobiera listę wszystkich zadań.                    |
| GET         | `/api/tasks/{id}`          | Pobiera jedno zadanie na podstawie identyfikatora. |
| POST        | `/api/tasks`               | Tworzy nowe zadanie.                               |
| PUT         | `/api/tasks/{id}`          | Aktualizuje istniejące zadanie.                    |
| PATCH       | `/api/tasks/{id}/complete` | Oznacza zadanie jako wykonane.                     |
| DELETE      | `/api/tasks/{id}`          | Usuwa zadanie z bazy danych.                       |

## Przykładowe żądania

### POST `/api/tasks`

**Body (JSON):**

```json
{
  "title": "Zakupy",
  "description": "Mleko, chleb, masło"
}
```

---

### PUT `/api/tasks/1`

**Body (JSON):**

```json
{
  "title": "Zakupy weekendowe",
  "description": "Mleko, chleb, masło, ser",
  "completed": false
}
```

> Endpointy **GET**, **PATCH** oraz **DELETE** nie wymagają przesyłania body.
