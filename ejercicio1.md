# 📘 Reporte de Ejercicio - HackerRank

**📅 Fecha:** 11-04-2025  
**🏷️ Título del reto:** Item List Manager  
**🌐 Enlace al reto:** [Ir al reto en hackerRank](https://www.hackerrank.com/challenges/item-list-manager/problem)  
**💻 Lenguaje usado:** `JavaScript (React)`  
**🎯 Nivel de dificultad:** `Fácil`

---

## 📄 Descripción del Reto

Crear una aplicación React sencilla llamada "Item List Manager". Esta aplicación muestra una lista de elementos y permite a los usuarios añadir nuevos. Los elementos se mostrarán en una lista desordenada y contará con un campo de entrada y un botón para añadir nuevos elementos.

## 💡 Lógica y solución utilizada

- Crear una funcion handleAddItem
- Se ejecuta cada vez que le das click al boton

1. Verdificamos si el input tiene contenido
2. De ser asi, guardamos en el estado de Items, un nuevo arreglo
3. el nuevo arreglo tendra la lista de elemnetos actuales en items mas el nuevo elemento
4. limpiamos el input atravez del estado que lo controla

### Código clave

```javascript
const handleAddItem = () => {
  // TODO: Add logic to add input to items list
  if (input) {
    setItems([...items, input]);
    setInput("");
  }
};
```

## 📚 Qué Aprendí

> 💡 **Aprendí** almacenar listas en los estados de react, actualizarlas unado el operador `...`

---

Edwin Cornejo 💚👨🏻‍💻
