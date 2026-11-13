# ChangeLog

# Release 0.1.0

## New

- `FirmwareRecord`, the record of the board a firmware image was built for, the firmware and its version, which the
  firmware puts in ESP-IDF's `.rodata_custom_desc` section, and a flasher reads from an image or a board with
  `FirmwareRecord::find`, so that it can refuse to flash firmware built for another board.
- `BOARD_TYPES`, the boards bruce-esp-idf supports, by ID and full name, with their chips, and `board_type` and
  `board_types_with_chip` to look them up, e.g. to ask which board is on a port when its firmware has no record.
- `no_std`, with no dependencies, for both firmware and flashers.
