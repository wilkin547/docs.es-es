---
title: "Sobrecarga de procedimiento (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ocultar mediante signatura"
  - "Overloads (palabra clave)"
  - "listas de parámetros"
  - "parámetros, listas"
  - "sobrecarga de procedimientos"
  - "procedimientos, varias versiones"
  - "procedimientos, sobrecargar"
  - "procedimientos, listas de parámetros"
  - "procedimientos, signaturas para"
  - "Shadows (palabra clave)"
  - "signaturas"
  - "signaturas, procedimiento"
  - "código de Visual Basic, listas de parámetros"
  - "código de Visual Basic, procedimientos"
ms.assetid: fbc7fb18-e3b2-48b6-b554-64c00ed09d2a
caps.latest.revision: 24
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 24
---
# Sobrecarga de procedimiento (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

*Sobrecargar* un procedimiento significa definirlo en varias versiones, utilizando el mismo nombre pero distintas listas de parámetros.  El propósito de sobrecargar un procedimiento es definir varias versiones de un procedimiento estrechamente relacionadas sin tener que distinguirlas por su nombre.  Esto se lleva a cabo modificando la lista de parámetros.  
  
## Reglas de sobrecarga  
 Cuando se sobrecarga un procedimiento, se aplican las siguientes reglas:  
  
-   **Mismo nombre**.  Todas las versiones sobrecargadas deben tener el mismo nombre de procedimiento.  
  
-   **Diferente firma**.  Cada versión sobrecargada debe diferir de todas las demás por lo menos en uno de los siguientes aspectos:  
  
    -   Número de parámetros  
  
    -   Orden de los parámetros  
  
    -   Tipos de datos de los parámetros  
  
    -   Número de parámetros de tipo \(para un procedimiento genérico\)  
  
    -   Tipo de valor devuelto \(sólo para un operador de conversión\)  
  
     Junto con el nombre de procedimiento, los elementos anteriores se denominan de forma colectiva *firma* del procedimiento.  Cuando llama a un procedimiento sobrecargado, el compilador utiliza la firma para comprobar que la llamada coincide exactamente con la definición.  
  
-   **Elementos que no forman parte de la firma**.  No se puede sobrecargar un procedimiento sin modificar la firma.  En concreto, no es posible sobrecargar un procedimiento cambiando únicamente uno o varios de los siguientes elementos:  
  
    -   Palabras clave que modifican a los procedimientos, como `Public`, `Shared` y `Static`  
  
    -   Nombres de parámetros o de parámetros de tipo  
  
    -   Restricciones de parámetros de tipo \(para un procedimiento genérico\)  
  
    -   Palabras clave que modifican a los parámetros, como `ByRef` y `Optional`  
  
    -   Si devuelve un valor  
  
    -   El tipo de datos del valor devuelto \(excepto para un operador de conversión\)  
  
     Los elementos de la lista anterior no forman parte de la firma.  Aunque no puede utilizarlos para diferenciar las versiones sobrecargadas, puede modificarlos en las versiones sobrecargadas que ya se diferencian debidamente por sus firmas.  
  
-   **Argumentos enlazados en tiempo de ejecución**.  Si piensa pasar una variable de objeto de enlace en tiempo de ejecución a un procedimiento sobrecargado, deberá declarar el parámetro correspondiente como <xref:System.Object>.  
  
## Varias versiones de un procedimiento  
 Supongamos que está escribiendo un procedimiento `Sub` para contabilizar una transacción en el saldo de un cliente, y que desea hacer referencia al cliente por su nombre o por su número de cuenta.  Para ello, puede definir dos procedimientos `Sub` diferentes, como se indica en este ejemplo:  
  
 [!code-vb[VbVbcnProcedures#73](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/procedure-overloading_1.vb)]  
  
### Versiones sobrecargadas  
 Una alternativa podría ser sobrecargar un único nombre de procedimiento.  Puede utilizar la palabra clave [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) para definir una versión del procedimiento para cada lista de parámetros, tal y como se indica a continuación:  
  
 [!code-vb[VbVbcnProcedures#72](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/procedure-overloading_2.vb)]  
  
#### Sobrecargas adicionales  
 Si también deseara aceptar el importe de una transacción en `Decimal` o `Single`, podría sobrecargar de nuevo `post` para que permitiera esa variación.  Si hiciera esto en cada una de las sobrecargas del ejemplo anterior, obtendría cuatro procedimientos `Sub`, todos ellos con el mismo nombre pero con cuatro firmas diferentes.  
  
## Ventajas de la sobrecarga  
 La ventaja de sobrecargar un procedimiento radica en la flexibilidad de la llamada.  Si utilizamos el procedimiento `post` declarado en el ejemplo anterior, el código de llamada puede obtener la identificación de cliente como `String` o `Integer`, y después llamar al mismo procedimiento en los dos casos.  Esto se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbcnProcedures#56](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/procedure-overloading_3.vb)]  
  
 [!code-vb[VbVbcnProcedures#57](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/procedure-overloading_4.vb)]  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Cómo: Definir varias versiones de un procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-multiple-versions-of-a-procedure.md)   
 [Cómo: Llamar a un procedimiento sobrecargado](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-overloaded-procedure.md)   
 [Cómo: Sobrecargar un procedimiento que toma parámetros opcionales](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [Cómo: Sobrecargar un procedimiento que toma un número indefinido de parámetros](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Consideraciones sobre la sobrecarga de procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)   
 [Resolución de sobrecargas](../../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)   
 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)   
 [Tipos genéricos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)