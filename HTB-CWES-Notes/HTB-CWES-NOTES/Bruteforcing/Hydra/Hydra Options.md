https://academy.hackthebox.com/module/57/section/504

**-S PORT**


| Parameter               | Explanation                                                                                                | Usage Example                                                                                                   |
| ----------------------- | ---------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| `-l LOGIN` or `-L FILE` | Login options: Specify either a single username (`-l`) or a file containing a list of usernames (`-L`).    | `hydra -l admin ...` or `hydra -L usernames.txt ...`                                                            |
| `-p PASS` or `-P FILE`  | Password options: Provide either a single password (`-p`) or a file containing a list of passwords (`-P`). | `hydra -p password123 ...` or `hydra -P passwords.txt ...`                                                      |
| `-t TASKS`              | Tasks: Define the number of parallel tasks (threads) to run, potentially speeding up the attack.           | `hydra -t 4 ...`                                                                                                |
| `-f`                    | Fast mode: Stop the attack after the first successful login is found.                                      | `hydra -f ...`                                                                                                  |
| `-s PORT`               | Port: Specify a non-default port for the target service.                                                   | `hydra -s 2222 ...`                                                                                             |
| `-v` or `-V`            | Verbose output: Display detailed information about the attack's progress, including attempts and results.  | `hydra -v ...` or `hydra -V ...` (for even more verbosity)                                                      |
| `service://server`      | Target: Specify the service (e.g., `ssh`, `http`, `ftp`) and the target server's address or hostname.      | `hydra ssh://192.168.1.100`                                                                                     |
| `/OPT`                  | Service-specific options: Provide any additional options required by the target service.                   | `hydra http-get://example.com/login.php -m "POST:user=^USER^&pass=^PASS^"` (for HTTP form-based authentication) |

