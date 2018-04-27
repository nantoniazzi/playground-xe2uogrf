# Conversor Celsius - Farenheit

[web]: http://www.ibserveis.com

Programa conversor. 
Prueba para curso iniciación a Elixir  [página web][web].

```elixir runnable

defmodule Funciones do
  
   def convertir(tipo, grados) do
    grados
     |> formula(tipo)   # es como si fuera  formula(grados,:tipo)
     |> redondear
     |> cadenapantalla
     |> IO.puts
   end

   defp formula(num,select) do
     case select do
       :aCel -> (num-32) * 5/9
       :aFah -> (num * 9/5) +32
     end
   end

   defp redondear(num), do: Float.round(num,2)

   defp cadenapantalla(num) do
    "El resultado es " <> Float.to_string(num) <> " Fahranheit"
   end
  
end

Funciones.convertir(:aCel,40)
Funciones.convertir(:aFah,10)

```

# Tech.io mola

If you want a more complex example (external libraries, viewers...), use the [Advanced Elixir template](https://tech.io/select-repo/1226)
