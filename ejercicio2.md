# 📘 Reporte de Ejercicio - HackerRank

**📅 Fecha:** 11-04-2025  
**🏷️ Título del reto:** Code Review Feedback  
**🌐 Enlace al reto:** [Ir al reto en hackerRank](https://www.hackerrank.com/challenges/code-review-feedback/problem)  
**💻 Lenguaje usado:** `JavaScript (React)`  
**🎯 Nivel de dificultad:** `Medio`

---

## 📄 Descripción del Problema

Crear una aplicación React llamada "Retroalimentación de la Revisión de Código" que registre y gestione la retroalimentación sobre diversos aspectos de la calidad del código. El componente debe permitir votar a favor y en contra de cada aspecto.

El componente CodeReviewFeedback muestra cinco aspectos: legibilidad, rendimiento, seguridad, documentación y pruebas.

## 💡 Lógica y solución utilizada

- Crear un componente card
- Con un map renderizar las card necesarias

1. Definir los estados de upVotes y downVotes con `useState`
2. En el `onClick` de cada boton incrementar 1 en el estado correspondiente (upVotes o downVotes)
3. Crear un arreglo con los cinco aspectos necesarios
4. Con una funcion map, renderizar un card por cada aspecto
5. cambiar los atributos `data-testid` para que sean unicos y se ejecutes las pruebas automaticas.

### Código clave

```javascript
import React, { useState } from "react";

const Card = ({ aspect, index }) => {
  const [upVotes, setUpVotes] = useState(0);
  const [downVotes, setDownVotes] = useState(0);
  return (
    <div className="flex wrap justify-content-center mt-30 gap-30">
      <div className="pa-10 w-300 card">
        <h2>{aspect}</h2>
        <div className="flex my-30 mx-0 justify-content-around">
          <button
            className="py-10 px-15"
            data-testid={`upvote-btn-${index}`}
            onClick={() => setUpVotes(upVotes + 1)}
          >
            👍 Upvote
          </button>
          <button
            className="py-10 px-15 danger"
            data-testid={`downvote-btn-${index}`}
            onClick={() => setDownVotes(downVotes + 1)}
          >
            👎 Downvote
          </button>
        </div>
        <p className="my-10 mx-0" data-testid={`upvote-count-${index}`}>
          Upvotes: <strong>{upVotes}</strong>
        </p>
        <p className="my-10 mx-0" data-testid={`downvote-count-${index}`}>
          Downvotes: <strong>{downVotes}</strong>
        </p>
      </div>
    </div>
  );
};

const FeedbackSystem = () => {
  const aspects = [
    "Readability",
    "Performance",
    "Security",
    "Documentation",
    "Testing",
  ];

  return (
    <div className="my-0 mx-auto text-center w-mx-1200">
      {aspects.map((aspect, index) => (
        <Card key={index} aspect={aspect} index={index} />
      ))}
    </div>
  );
};

export default FeedbackSystem;
```

## 📚 Qué Aprendí

> ❓ El reto funcionaba pero no pasaba los test cases, ¿por que?  
> 💡Lo que paso es que HackerRank usa pruebas automatizadas entonces buscan elementos por su `data-testid` y todos los elentos tenian el mismo `data-testid`, **entonces** si o si, se tienen que usar un `data-testid` unico para cada item.
> `data-testid` **funciona** para encontrar componentes espesificos y simular clics o verificar su contenido, cuando se hacen tests.
> Pero **que es el `data-testid`** bueno, HTML permite crear atributos personalizados, simplemente agregando el prefijo **data-** y depues el nombre de nuestro atributo, son **utiles** ya que no afecta el estilo ni la funcionalidad, por eso se usan en pruebas.

---

Edwin Cornejo 💚👨🏻‍💻
