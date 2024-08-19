# RICH
```
from rich.console import Console
from rich.table import Table
from rich import box
from rich import print
from rich.panel import Panel

# TABLE
console = Console()
table = Table(show_header=True, box=box.SIMPLE_HEAD, header_style="bold magenta")
table.add_column("Interface")
table.add_column("MAC Address")
table.add_column("IPv4 Address")

table.add_row(iface,mac,ipv4)

console.print(table)

# COLORS
print("[green]HELLO WORLD[/]")
console.print("[green]HELLO WORLD[/]")

# LOGS
console.log("THIS IS A LOG", style="info")

# PANEL
print(Panel.fit("[green]some text[/]"))
```