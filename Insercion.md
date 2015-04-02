#** ALGORITMO DE INSERCION SORT**
**El ordenamiento por inserción** (insertion sort en inglés) es una manera muy natural de ordenar para un ser humano, y puede usarse fácilmente para ordenar un mazo de cartas numeradas en forma arbitraria. Requiere O(n²) operaciones para ordenar una lista de n elementos.

Inicialmente se tiene un solo elemento, que obviamente es un conjunto ordenado. Después, cuando hay k elementos ordenados de menor a mayor, se toma el elemento k+1 y se compara con todos los elementos ya ordenados, deteniéndose cuando se encuentra un elemento menor (todos los elementos mayores han sido desplazados una posición a la derecha) o cuando ya no se encuentran elementos (todos los elementos fueron desplazados y este es el más pequeño). En este punto se inserta el elemento k+1 debiendo desplazarse los demás elementos

●Código
```Scala
object HelloWorld {
  def main(args: Array[String]) {
    val A = Array(2, 300, 45, 18, 29)
    var insertion = new InsertionSort()

    insertion.sort(A, true)

    for (number <- A) {
      println(number)
    }
  }
}
```

```Scala
class InsertionSort{
  def sort(A: Array[Int], asc: Boolean){
    var key = 0
    var i = 0

    for (j <- 1 to A.length - 1) {
      key = A(j)
      i = j - 1
      while (i >= 0 && compare(A(i), key, asc)) {
        A(i + 1) = A(i)
        i = i - 1
      }
      A(i + 1) = key
    }n
  }

  def compare(a: Int, b: Int, asc: Boolean): Boolean = {
    if (true == asc) {
      return a > b
    }
    return a <= b
  }
}

```
![Insercion ](http://es.wikipedia.org/wiki/Ordenamiento_por_inserci%C3%B3n#mediaviewer/File:Insertion-sort-example-300px.gif)


