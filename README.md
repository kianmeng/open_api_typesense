# OpenApiTypesense

[![Hex.pm](https://img.shields.io/hexpm/v/open_api_typesense)](https://hex.pm/packages/open_api_typesense)
[![Hexdocs.pm](https://img.shields.io/badge/hex-docs-lightgreen.svg)](https://hexdocs.pm/open_api_typesense)
[![Hex.pm](https://img.shields.io/hexpm/l/open_api_typesense)](https://hexdocs.pm/open_api_typesense/license.html)
[![Typesense badge](https://img.shields.io/badge/Typesense-v27.1-darkblue)](https://typesense.org/docs/27.1/api)
[![Coverage Status](https://coveralls.io/repos/github/jaeyson/open_api_typesense/badge.svg?branch=main)](https://coveralls.io/github/jaeyson/open_api_typesense?branch=main)

## TODO
- Custom Http client adapter (currently [`Req`](https://hexdocs.pm/req))
- Tests for each modules not completed yet.
- Where to consume `opts`:
```elixir
  def take_snapshot(conn \\ Connection.new(), opts \\ []) do
    client = opts[:client] || @default_client
    query = Keyword.take(opts, [:snapshot_path])

    client.request(conn, %{
      args: [],
      call: {OpenApiTypesense.Operations, :take_snapshot},
      url: "/operations/snapshot",
      method: :post,
      query: query,
      response: [{201, {OpenApiTypesense.SuccessStatus, :t}}],
      opts: opts # <-- TODO
    })
  end
```


## Installation

If [available in Hex](https://hex.pm/docs/publish), the package can be installed
by adding `open_api_typesense` to your list of dependencies in `mix.exs`:

```elixir
def deps do
  [
    {:open_api_typesense, "~> 0.2"}
  ]
end
```

Documentation can be generated with [ExDoc](https://github.com/elixir-lang/ex_doc)
and published on [HexDocs](https://hexdocs.pm). Once published, the docs can
be found at <https://hexdocs.pm/open_api_typesense>.

