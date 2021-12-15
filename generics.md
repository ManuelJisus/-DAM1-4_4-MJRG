fun main() {
    var numbers = listOf("one", "two", "three", "four")
    var numbersRev = reverse(numbers)
    if (!listOf("four", "three", "two", "one").equals(numbersRev))
        println("Error")
    else
        println("Correcto")
    println(numbersRev)
}

class Pila<T>() {
    private var pila = mutableListOf<T>()

    // Devuelve el elemento en la cabeza de la pila.
    fun tope() {
        pila.lastIndex

    }

    // Insertar o apilar
    fun push(element: T) {
        pila.add(element)
    }

    //Eliminar o desapilar
    fun pop() : T {
         return pila.removeAt(pila.lastIndex)

    }

    // Esta vacia??
    fun vacia(): Boolean {
        if (pila.isEmpty()) {
            return true
        }
        return false
    }


}

fun <T> reverse(lista: List<T>) : List<T> {
    var pila: Pila<T> = Pila()

    var iterador = lista.listIterator()
    var list = mutableListOf<T>()

    while (iterador.hasNext()) {
        pila.push(iterador.next())
    }
    while (!pila.vacia()) {
        list.add(pila.pop())
    }
    return list
}
