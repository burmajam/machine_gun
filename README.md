# MachineGun

HTTP client for Elixir. Based on [Gun](https://github.com/ninenines/gun) and [Poolboy](https://github.com/devinus/poolboy). Supports HTTP/1 and HTTP/2 with automatic detection. Maintains separate connection pool for each host:port combination. Drop-in replacement for [HTTPoison](https://github.com/edgurgel/httpoison).

## Example

```
%MachineGun.Response{body: body, status_code: 200} =
  MachineGun.get!(
    "https://ifconfig.co", [{"accept", "text/plain"}],
    %{:request_timeout => 5000, :pool_group => :default})
```

## Configuration

```
config :machine_gun,
  default: %{
    :pool_size => 4,
    :pool_max_overflow => 4,
    :pool_timeout => 1000
  }
```