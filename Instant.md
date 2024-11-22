### What is `Instant` in Kotlin?

An `Instant` represents a specific moment in time in UTC (Coordinated Universal Time), with precision up to nanoseconds. It is part of the `java.time` package and is ideal for handling timestamps without the complexity of time zones.

#### Key Features:
1. **Timezone-Independent**: Always represents time in UTC.
2. **Precise**: Tracks time with nanosecond accuracy.
3. **Universal**: The same `Instant` represents the exact same moment worldwide.

#### Usage:
- **Get Current Time**:
  ```kotlin
  val now = Instant.now()
  ```

- **Create an Instant**:
  ```kotlin
  // From epoch seconds
  val fromEpoch = Instant.ofEpochSecond(1634572800)

  // From ISO-8601 string
  val parsed = Instant.parse("2024-11-22T10:00:00Z")
  ```

- **Manipulate Time**:
  ```kotlin
  val oneHourLater = Instant.now().plusSeconds(3600)
  val fiveMinutesEarlier = Instant.now().minusSeconds(300)
  ```

- **Convert to Local Time**:
  ```kotlin
  val localTime = Instant.now().atZone(ZoneId.systemDefault())
  ```

#### Example:
```kotlin
import java.time.Instant

fun main() {
    val start = Instant.now()

    // Simulate processing
    Thread.sleep(2000)

    val end = Instant.now()

    println("Duration in seconds: ${end.epochSecond - start.epochSecond}")
}
```

#### Why Use `Instant`?
- **Simplicity**: Avoid time zone confusion by working directly in UTC.
- **Accuracy**: Perfect for logging events or calculating durations.
- **Interoperability**: Works seamlessly with Kotlin and Java time libraries.
