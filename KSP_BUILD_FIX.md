# Shipon Store — KSP Build Fix

The GitHub Actions log reached `:app:kspDebugKotlin` and reported:

- `SyncQueueDao.kt:14: [MissingType]`
- `RoomKspProcessor was unable to process AppDatabase`

The source-level cause in `SyncQueueDao.kt` was `OnConflictStrategy.APPEND`. Room's `OnConflictStrategy` does not define `APPEND`; the DAO now uses `OnConflictStrategy.ABORT`, which matches the other insert DAOs and preserves the intended append/new-row behavior for the auto-generated queue ID.

The project remains on KSP + Room. No KAPT plugin/dependency was reintroduced.
