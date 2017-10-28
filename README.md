# Sequence

More advanced supervision using a Tree.

Taken from programming elixir book ...

```
$ iex -S mix
Compiling 6 files (.ex)
Generated sequence app
iex> Sequence.Server.next_number
123
iex> Sequence.Server.next_number
124
iex> Sequence.Server.increment_number 100
:ok
iex> Sequence.Server.next_number
225
iex> Sequence.Server.increment_number "cause it to crash"
:ok
iex>
14:35:07.337 [error] GenServer Sequence.Server terminating
Last message: {:"$gen_cast", {:increment_number, "cause it to crash"}}
State: {226, #PID<0.70.0>}
** (exit) an exception was raised:
** (ArithmeticError) bad argument in arithmetic expression
(sequence) lib/sequence/server.ex:32: Sequence.Server.handle_cast/2
Chapter 18. OTP: Supervisors • 236
Prepared exclusively for Adam R Seldon report erratum • discuss
(stdlib) gen_server.erl:599: :gen_server.handle_msg/5
(stdlib) proc_lib.erl:239: :proc_lib.init_p_do_apply/3
iex> Sequence.Server.next_number
226
```

## Installation

If [available in Hex](https://hex.pm/docs/publish), the package can be installed
by adding `sequence2` to your list of dependencies in `mix.exs`:

```elixir
def deps do
  [
    {:sequence2, "~> 0.1.0"}
  ]
end
```

Documentation can be generated with [ExDoc](https://github.com/elixir-lang/ex_doc)
and published on [HexDocs](https://hexdocs.pm). Once published, the docs can
be found at [https://hexdocs.pm/sequence2](https://hexdocs.pm/sequence2).

