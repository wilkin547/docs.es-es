---
title: "Llamar a una propiedad o m&#233;todo mediante un nombre de cadena (Visual Basic) | Microsoft Docs"
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
  - "CallByName (función)"
  - "llamar a métodos, nombres de cadenas"
  - "llamadas a métodos, cadenas"
  - "métodos [Visual Basic], llamar con nombres de cadenas"
  - "objetos [Visual Basic], establecer propiedades"
  - "pasar operadores"
  - "propiedades [Visual Basic], establecer en tiempo de ejecución"
  - "establecer propiedades, propiedades de objetos en tiempo de ejecución"
  - "cadenas [Visual Basic], pasar operadores nuevos como"
ms.assetid: 79a7b8b4-b8c7-4ad8-aca8-12a9a2b32f03
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Llamar a una propiedad o m&#233;todo mediante un nombre de cadena (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

En la mayoría de los casos, puede detectar las propiedades y métodos de un objeto en tiempo de diseño y escribir código para controlarlos.  No obstante, en algunos casos, puede que no conozca de antemano las propiedades y los métodos de un objeto o que simplemente desee la flexibilidad de permitir a un usuario final que especifique propiedades o ejecute métodos en tiempo de ejecución.  
  
## CallByName \(Función\)  
 Piense, por ejemplo, en una aplicación cliente que evalúe expresiones escritas por el usuario mediante el paso de un operador a un componente COM.  Suponga que está agregando constantemente funciones nuevas al componente que requiere operadores nuevos.  Cuando use las técnicas estándar de acceso a objetos, debe compilar y distribuir de nuevo la aplicación cliente para poder utilizar los operadores nuevos.  Para evitarlo, puede utilizar la función `CallByName` para pasar los operadores nuevos como cadenas, sin modificar la aplicación.  
  
 La función `CallByName` le permite utilizar una cadena para especificar una propiedad o método en tiempo de ejecución.  La firma para la función `CallByName` tiene el siguiente aspecto:  
  
 *Resultado* \= `CallByName`\(*Objeto*, *nombreDeProcedimiento*, *tipoDeLlamada*, *Argumentos*\(\)\)  
  
 El primer argumento, *Objeto*, toma el nombre del objeto sobre el que desea actuar.  El argumento *nombreDeProcedimiento* toma una cadena que contiene el nombre del procedimiento de propiedad o método que debe invocarse.  El argumento *tipoDeLlamada* toma una constante que representa el tipo de procedimiento que debe invocarse: un método \(`Microsoft.VisualBasic.CallType.Method`\), una lectura de propiedad \(`Microsoft.VisualBasic.CallType.Get`\) o un conjunto de propiedades \(`Microsoft.VisualBasic.CallType.Set`\).  El argumento *Argumentos*, que es opcional, toma una matriz de tipo `Object` que contiene los argumentos para el procedimiento.  
  
 Puede utilizar `CallByName` con clases en la solución actual, pero se utiliza más frecuentemente para obtener acceso a objetos COM o a objetos de ensamblados de [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)].  
  
 Suponga que agrega una referencia a un ensamblado que contiene una clase denominada `MathClass`, que tiene una función nueva denominada `SquareRoot`, como se muestra en el siguiente código:  
  
 [!code-vb[VbVbalrOOP#53](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_1.vb)]  
  
 La aplicación podría utilizar controles de cuadro de texto para controlar qué método se va a llamar y sus argumentos.  Por ejemplo, si `TextBox1` contiene la expresión que se va a evaluar y `TextBox2` se utiliza para escribir el nombre de la función, puede utilizar el siguiente código para invocar la función `SquareRoot` en la expresión de `TextBox1`:  
  
 [!code-vb[VbVbalrOOP#54](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_2.vb)]  
  
 Si escribe "64" en `TextBox1`, "SquareRoot" en `TextBox2` y, a continuación, llama al procedimiento `CallMath`, se evalúa la raíz cuadrada del número que aparece en `TextBox1`.  El código del ejemplo invoca la función `SquareRoot` \(que toma una cadena con la expresión que se va a evaluar como argumento requerido\) y devuelve "8" en `TextBox1` \(la raíz cuadrada de 64\).  Si el usuario escribe una cadena no válida en `TextBox2`, o si la cadena contiene el nombre de una propiedad en lugar de un método, o si el método tiene un argumento necesario adicional, sin duda se producirá un error en tiempo de ejecución.  Debe agregar un código de control de errores sólido cuando use `CallByName` para prever estos errores u otros.  
  
> [!NOTE]
>  Mientras que la función `CallByName` puede ser útil en algunas situaciones, debe sopesar su utilidad frente a las implicaciones de rendimiento; el uso de `CallByName` para invocar un procedimiento es un poco más lento que una llamada enlazada en tiempo de ejecución.  Si está invocando una función a la que se llama repetidamente, como ocurriría dentro de un bucle, `CallByName` puede afectar de forma grave al rendimiento.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>   
 [Determinar el tipo de objeto](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)