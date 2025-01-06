The Music Store Analysis project demonstrates the use of SQL to analyze data from a music store database. This analysis helps derive actionable insights into sales performance, customer behavior, and inventory trends.
Database Schema
1. Artist

    ArtistId (Primary Key)
    Name

2. Album

    AlbumId (Primary Key)
    Title
    ArtistId (Foreign Key referencing Artist.ArtistId)

3. Track

    TrackId (Primary Key)
    Name
    AlbumId (Foreign Key referencing Album.AlbumId)
    MediaTypeId (Foreign Key referencing MediaType.MediaTypeId)
    GenreId (Foreign Key referencing Genre.GenreId)
    Composer
    Milliseconds
    Bytes
    UnitPrice

4. MediaType

    MediaTypeId (Primary Key)
    Name

5. Genre

    GenreId (Primary Key)
    Name

6. Playlist

    PlaylistId (Primary Key)
    Name

7. PlaylistTrack

    PlaylistId (Composite Key, Foreign Key referencing Playlist.PlaylistId)
    TrackId (Composite Key, Foreign Key referencing Track.TrackId)

8. Customer

    CustomerId (Primary Key)
    FirstName
    LastName
    Company
    Address
    City
    State
    Country
    PostalCode
    Phone
    Fax
    Email
    SupportRepId (Foreign Key referencing Employee.EmployeeId)

9. Invoice

    InvoiceId (Primary Key)
    CustomerId (Foreign Key referencing Customer.CustomerId)
    InvoiceDate
    BillingAddress
    BillingCity
    BillingState
    BillingCountry
    BillingPostalCode
    Total

10. InvoiceLine

    InvoiceLineId (Primary Key)
    InvoiceId (Foreign Key referencing Invoice.InvoiceId)
    TrackId (Foreign Key referencing Track.TrackId)
    UnitPrice
    Quantity

11. Employee

    EmployeeId (Primary Key)
    LastName
    FirstName
    Title
    ReportsTo (Foreign Key referencing Employee.EmployeeId)
    BirthDate
    HireDate
    Address
    City
    State
    Country
    PostalCode
    Phone
    Fax
    Email

Relationships
Artist - Album: One-to-Many (An artist can have multiple albums).
Album - Track: One-to-Many (An album can have multiple tracks).
Track - MediaType: Many-to-One (A track belongs to one media type).
Track - Genre: Many-to-One (A track belongs to one genre).
Playlist - PlaylistTrack - Track: Many-to-Many (A track can belong to multiple playlists).
Customer - Invoice: One-to-Many (A customer can have multiple invoices).
Invoice - InvoiceLine: One-to-Many (An invoice can have multiple invoice lines).
Track - InvoiceLine: One-to-Many (A track can appear in multiple invoice lines).
Employee - Customer: One-to-Many (An employee can support multiple customers).
Employee - Employee: Self-referencing (An employee can report to another employee).
