# Sources — 34401A.komand

Every change to this table that a vendor manual confirms, with where the manual says it (AUDIO.komand `check-tables --strict` research, 2026-10-31). A finding no manual confirmed is listed under *Not confirmed* with what was searched, and the table is left as it was.

## HP 34401A Multimeter User's Guide (34401-90004), Chapter 4 Remote Interface Reference — Math Operation Commands

read at ManualsLib (pages cited are the printed ones) — <https://www.manualslib.com/manual/578999/Hp-34401a.html?page=125>

| Command | Change | Manual |
|---|---|---|
| `set/Set_dB_Ref` | arg = `{"kind": "numeric", "unit": "dBm", "min": -200, "max": 200}` | CALCulate:DB:REFerence, p. 125 — stores a relative value in the dB Relative Register, –200.00 dBm to 200.00 dBm — a level, not an enum |
| `set/Set_dBm_Ref` | arg = `{"kind": "enum", "values": ["50", "75", "93", "110", "124", "125", "135", "150", "250", "300", "500", "600", "800", "900", "1000", "1200", "8000"], "unit": "ohm"}` | CALCulate:DBM:REFerence, p. 126 — "Choose from: 50, 75, 93, 110, 124, 125, 135, 150, 250, 300, 500, 600, 800, 900, 1000, 1200, or 8000 ohms" |

### Not confirmed (left as is)

- `set/Set_Db_Reference` — searched: 34401-90004 pp. 125 and 168 name the node only as `CALCulate:DB:REFerence`; a bare `:DB:REFerence` (this entry) is not on those pages. The node is `Set_dB_Ref` above — re-pointing or retiring this entry is the owner's call
- `set/Set_Rang` — searched: 34401-90004 p. 121 (Measurement Configuration Commands) gives the range node as `<function>:RANGe {<range>|MINimum|MAXimum}`, per function; this entry's bare `RANG <value>` names no function, so no arg block is confirmed for it
- `set/Set_Rang_Auto` — searched: p. 121, `<function>:RANGe:AUTO {OFF|ON}`; as Set_Rang, the bare `RANG:AUTO` names no function
- `set/Set_Sens_Volt_Nplc` — searched: ManualsLib pp. 121, 125–126, 167–169 of 34401-90004; the NPLC command's page was not reached, so its legal values are not confirmed here
- `do/Do_Data_Points?_All` — searched: same pages; `DATA:POINts? ALL` was not found in what was read
- `nab/Get_Read_All` — searched: same pages; `READ:ALL?` was not found in what was read

## Retired (owner decision, 2026-10-31)

The manual shows these commands do not exist. Each entry stays in the table with `"retired": true` and its citation in `retired_because`; KOMAND never sends it, check-tables skips it, and it still counts toward the commands floor.

- `set/Set_Db_Reference` — HP 34401A User's Guide 34401-90004 (https://www.manualslib.com/manual/578999/Hp-34401a.html) pp. 125, 168: the node is CALCulate:DB:REFerence (table entry Set_dB_Ref); a bare :DB:REFerence is not a 34401A command
- `set/Set_Rang` — HP 34401A User's Guide 34401-90004 (https://www.manualslib.com/manual/578999/Hp-34401a.html) p. 121: ranges are <function>:RANGe {<range>|MIN|MAX} per function; a bare RANG names no function
- `set/Set_Rang_Auto` — HP 34401A User's Guide 34401-90004 (https://www.manualslib.com/manual/578999/Hp-34401a.html) p. 121: <function>:RANGe:AUTO {OFF|ON} per function; a bare RANG:AUTO names no function
- `set/Set_Sens_Volt_Nplc` — HP 34401A User's Guide 34401-90004 (https://www.manualslib.com/manual/578999/Hp-34401a.html) p. 122: <function>:NPLCycles {0.02|0.2|1|10|100|MIN|MAX} per function (VOLTage:DC, not VOLTage); SENS:VOLT:NPLC names no function
- `do/Do_Data_Points?_All` — HP 34401A User's Guide 34401-90004 (https://www.manualslib.com/manual/578999/Hp-34401a.html): `DATA:POINts? ALL` appears on none of pp. 118-131, 168 read; DATA:POINts? is a query, not a do-press (owner decision 2026-10-31)
- `nab/Get_Read_All` — HP 34401A User's Guide 34401-90004 (https://www.manualslib.com/manual/578999/Hp-34401a.html) p. 130: the reading query is READ? with no parameter; there is no READ:ALL?

## SCPI paths — every header against the model's own tree (scpi_paths.py, 2026-11-11)

The tree: `34401A.scpi.json`, read off HP 34401A User's Guide 34401-90004 (Feb 1996), Chapter 4 Remote Interface Reference, SCPI Command Summary pp. 104-111; [SENSe:] is the default node. Each entry's `notes` / `retired_because` carries the full reason and page; the 33220A's Certify of 2026-11-11 (199 tries) and the GUI-certificate book are the bench evidence. Nothing was sent to verify.

| Command | Change | Was |
|---|---|---|
| `set/Set_Limit_Lower` | scpi → `:CALCulate:LIMit:LOWer <value>` | was `:LIMit:LOWer <value>` |
| `set/Set_Limit_Upper` | scpi → `:CALCulate:LIMit:UPPer <value>` | was `:LIMit:UPPer <value>` |
| `set/Set_Null_Offset_Alt` | scpi → `:CALCulate:NULL:OFFSet <value>` | was `:NULL:OFFSet <value>` |
| `set/Set_Questionable_Enable` | scpi → `:STATus:QUEStionable:ENABle <value>` | was `:QUEStionable:ENABle <value>` |
| `set/Set_Secure_State` | scpi → `:CALibration:SECure:STATe <value>` | was `:SECure:STATe <value>` |
| `do/Do_Secure_Code` | scpi → `:CALibration:SECure:CODE` | was `:SECure:CODE` |
| `do/Do_Text_Clear` | scpi → `:DISPlay:TEXT:CLEar` | was `:TEXT:CLEar` |
| `nab/Get_Average_Average` | scpi → `:CALCulate:AVERage:AVERage?` | was `:AVERage:AVERage?` |
| `nab/Get_Average_Count` | scpi → `:CALCulate:AVERage:COUNt?` | was `:AVERage:COUNt?` |
| `nab/Get_Db_Reference` | scpi → `:CALCulate:DB:REFerence?` | was `:DB:REFerence?` |
| `nab/Get_Limit_Lower` | scpi → `:CALCulate:LIMit:LOWer?` | was `:LIMit:LOWer?` |
| `nab/Get_Limit_Upper` | scpi → `:CALCulate:LIMit:UPPer?` | was `:LIMit:UPPer?` |
| `nab/Get_Null_Offset` | scpi → `:CALCulate:NULL:OFFSet?` | was `:NULL:OFFSet?` |
| `nab/Get_Questionable_Enable` | scpi → `:STATus:QUEStionable:ENABle?` | was `:QUEStionable:ENABle?` |
| `nab/Get_Questionable_Event` | scpi → `:STATus:QUEStionable:EVENt?` | was `:QUEStionable:EVENt?` |
| `nab/Get_Secure_State` | scpi → `:CALibration:SECure:STATe?` | was `:SECure:STATe?` |
| `set/Set_AC_Bandwidth` | scpi → `:SENSe:DETector:BANDwidth <filter>` | was `:SENSe:VOLTage:AC:BANDwidth <filter>` |
| `do/Do_Back_Goto` | retired — Retired: the 34401A manual (34401-90004 Ch. 4 SCPI Command Summary) has no such command — `BACK:GOTO` is two words of the "Using the Status Registers" prose the scraper read as a header. |  |
| `do/Do_Dcv_Dcv` | retired — Retired: the 34401A manual (34401-90004 Ch. 4 SCPI Command Summary) has no such command — `DCV:DCV` is not a SCPI header; DC volts is `CONFigure:VOLTage:DC` / `MEASure:VOLTage:DC?`. |  |
| `rig/Config_Temperature` | retired — Retired: the 34401A manual (34401-90004 Ch. 4 SCPI Command Summary) has no such command — the 34401A measures no temperature: CONFigure has VOLTage, CURRent, RESistance, FRESistance, FREQuency, PERiod, CONTinuity and DIODe only. |  |

### Return formats and argument kinds (same audit, 2026-11-11)

| Command | Change |
|---|---|
| `nab/Get_Calculate_Average_Count`, `Get_Average_Count`, `Query_Average`, `Get_Average_Average`, `Get_Fresistance_Nplcycles`, `Get_Resolution_Nplcycles`, `Get_Trigger_Count` | returns NR3 (was NR1) — the unit answers in exponent form on the bench |
| `nab/Get_Measure_Continuity` | returns NR3 Ω (was BOOL) — a reading, 9.90000000E+37 when open |
| `nab/Get_Db_Reference`, `Get_Calculate_Db_Reference` | returns NR3 dBm (was CRD) |
