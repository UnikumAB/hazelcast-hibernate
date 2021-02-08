Changes:

- Remove Caffeine shading to get the official package names for other
  libraries to use. Caffeine will in other words no more be embedded
  within the jar.
- To make the library compile with Java 11:
  * Add JAXB dependencies.
  * Disable PhoneHomeTest as it fails with Java11s package isolation.
- Add getCaffeine() method to LocalRegionCache to expose the Caffeine instance,
- Make class PhoneHomeService public so that constructors can be overridden.
- Enable recordStats() on caches.
- Replace use of Cache.asMap() with calls via the Cache object where applicable
  as the former bypasses any statistics recording.