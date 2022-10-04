# Date and Time

## Calendar data

The `java.time` package is the main package of the date/time framework.
The machine view of time is the number of milliseconds that have elapsed since the Epoch.

- Based on the ISO calender system
- All classes are `immutable` and `thread` safe
- Clear seperation between machine and human view of time

The following are the different types

- `Instant`: Represents the machine view of time
- `LocalDate/LocalTime/LocalDateTime/ZonedDateTime` represent human view of time.
- Use specific types to capture different components
- `Period` represents a date in terms of Days Months and Years only
- `Duration` represents the time-based amount of time in terms of Hours Minutes and Seconds
- Can use `enums` `Month` and `DayOfWeek`
- Various methods

## Calender Data

- All classes are immutable and thread-safe
- `Instant` - number of miliseconds since the epoch
- `Local<Date/Time/DateTime>` and `ZoneDateTime` represent human view of time
- `Period` a date-based amount of time in terms of Days, Months and Years
- `Duration` represents time based in terms of Hours, Minutes and Seconds
- NO date/time classes have a constructor.

### of-methods

```java
static LocalDate of(int year, ,<int/Month month>, int dayOfMonth)
```

```java
static LocalTime of(int hour, int minute (int second (int nanoOfSecond) ) )
```

```java
static LocalDateTime of(LocalDate date, LocalTime time)
```

- Indexing for month starts from 1, hours start from 0-23
- Throws `DateTimeException` (unchecked)

---
