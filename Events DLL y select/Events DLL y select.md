# Locations

| location_id | name                   | address             | city           | state | country        | postal_code |
|-------------|------------------------|---------------------|----------------|-------|----------------|-------------|
| 1           | Centro de Convenciones | 123 Calle Principal| Ciudad de México| CDMX  | México         | 12345       |
| 2           | Estadio Nacional       | 456 Avenida Central| Bogotá         |       | Colombia       | 54321       |
| 3           | Teatro Municipal       | 789 Calle Broadway | Nueva York     | NY    | Estados Unidos| 10001       |
| 4           | Centro de Exposiciones | 321 Calle Expo     | Madrid         |       | España         | 28001       |
| 5           | Centro de Conferencias | 555 Rue Conférence | París          |       | Francia        | 75001       |

# Events

| event_id | title            | description                            | start_date          | end_date            |
|----------|------------------|----------------------------------------|---------------------|---------------------|
| 1        | Concierto de música | Un gran evento musical               | 2024-06-15 18:00:00| 2024-06-15 23:00:00|
| 2        | Tech Conference  | Conferencia anual de tecnología        | 2024-07-20 09:00:00| 2024-07-20 17:00:00|
| 3        | Art Expo         | Exposición de arte moderno             | 2024-08-05 10:00:00| 2024-08-05 18:00:00|
| 4        | Food Festival    | Deliciosa comida de todo el mundo      | 2024-09


CREATE TABLE IF NOT EXISTS Locations (
    location_id SERIAL PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    address VARCHAR(255) NOT NULL,
    city VARCHAR(100) NOT NULL,
    state VARCHAR(100),
    country VARCHAR(100) NOT NULL,
    postal_code VARCHAR(20)
);

CREATE TABLE IF NOT EXISTS Events (
    event_id SERIAL PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    description TEXT,
    start_date TIMESTAMP NOT NULL,
    end_date TIMESTAMP NOT NULL
);

CREATE TABLE IF NOT EXISTS Attendees (
    attendee_id SERIAL PRIMARY KEY,
    first_name VARCHAR(100) NOT NULL,
    last_name VARCHAR(100) NOT NULL,
    email VARCHAR(255) UNIQUE NOT NULL,
    phone VARCHAR(20),
    registration_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

INSERT INTO Locations (name, address, city, state, country, postal_code)
 VALUES
('Centro de Convenciones', '123 Calle Principal', 'Ciudad de México', 'CDMX', 'México', '12345'),
('Estadio Nacional', '456 Avenida Central', 'Bogotá', NULL, 'Colombia', '54321'),
('Teatro Municipal', '789 Calle Broadway', 'Nueva York', 'NY', 'Estados Unidos', '10001'),
('Centro de Exposiciones', '321 Calle Expo', 'Madrid', NULL, 'España', '28001'),
('Centro de Conferencias', '555 Rue Conférence', 'París', NULL, 'Francia', '75001');

INSERT INTO Attendees (first_name, last_name, email, phone) 
VALUES
('Juan', 'Pérez', 'juan.perez@example.com', '+1234567890'),
('María', 'González', 'maria.gonzalez@example.com', '+0987654321'),
('Carlos', 'Martínez', 'carlos.martinez@example.com', NULL),
('Ana', 'López', 'ana.lopez@example.com', '+1555666777'),
('Pedro', 'Rodríguez', 'pedro.rodriguez@example.com', '+3445566778');

INSERT INTO Events (title, description, start_date, end_date) 
VALUES
('Concierto de música', 'Un gran evento musical', '2024-06-15 18:00:00', '2024-06-15 23:00:00'),
('Tech Conference', 'Conferencia anual de tecnología', '2024-07-20 09:00:00', '2024-07-20 17:00:00'),
('Art Expo', 'Exposición de arte moderno', '2024-08-05 10:00:00', '2024-08-05 18:00:00'),
('Food Festival', 'Deliciosa comida de todo el mundo', '2024-09-10 11:00:00', '2024-09-10 20:00:00'),
('Feria del Libro', 'Un encuentro para los amantes de los libros', '2024-10-25 09:00:00', '2024-10-25 16:00:00');
![[Captura de pantalla 2024-05-22 174724.png]]![[Captura de pantalla 2024-05-22 174605.png]]![[Captura de pantalla 2024-05-22 174113.png]]![[Captura de pantalla 2024-05-22 174437.png]]![[Captura de pantalla 2024-05-22 173920.png]]