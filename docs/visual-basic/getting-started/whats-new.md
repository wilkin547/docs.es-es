---
title: "What&#39;s New for Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VB.StartPage.WhatsNew"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "new features, Visual Basic"
  - "what's new [Visual Basic]"
  - "Visual Basic, what's new"
ms.assetid: d7e97396-7f42-4873-a81c-4ebcc4b6ca02
caps.latest.revision: 145
caps.handback.revision: 145
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# What&#39;s New for Visual Basic
[!INCLUDE[vs2017banner](../../csharp/includes/vs2017banner.md)]

Esta página enumera los nombres de las características clave de cada versión de Visual Basic con descripciones de las características nuevas y mejoradas de la versión más reciente del lenguaje.  
  
## Versiones anteriores  
 Visual Basic \/ Visual Studio .NET 2002  
 Primera versión  
  
 Visual Basic \/ Visual Studio .NET 2003  
 Operadores de desplazamiento de bits, declaración de variable de bucle  
  
 Visual Basic \/ Visual Studio .NET 2005  
 Tipo `My` y tipos auxiliares \(acceso a la aplicación, equipo, sistema de archivos, red\)  
  
 Visual Basic \/ Visual Studio .NET 2008  
 Language Integrated Query \(LINQ\), literales XML, inferencia de tipo de variable local, inicializadores de objeto, tipos anónimos, métodos de extensión, inferencia de tipo de variable local `var`, expresiones lambda, operador `if`, métodos parciales, tipos de valor que aceptan valores null  
  
 Visual Basic \/ Visual Studio .NET 2010  
 Propiedades autoimplementadas, inicializadores de colección, continuación de línea implícita, dinámica, covarianza\/contravarianza genérica, acceso de espacio de nombres global  
  
 Visual Basic \/ Visual Studio .NET 2012  
 `Async` \/ `await`, iteradores, atributos de información de llamador  
  
 Visual Basic \/ Visual Studio .NET 2013  
 Vistas previas de tecnología de .NET Compiler Platform \(«Roslyn»\)  
  
 Visual Basic \/ Visual Studio .NET 2015  
 Versión actual, véase más abajo  
  
## Versión actual  
 [Nameof](../../csharp/language-reference/keywords/nameof.md)  
 Puede obtener el nombre de cadena no calificado de un tipo o miembro para usarlo en un mensaje de error sin codificar de forma rígida una cadena.  Esto permite que el código siga siendo correcto al refactorizarlo.  Esta característica también es útil para enlazar los vínculos MVC del controlador de vista de modelos y desencadenar eventos de propiedad cambiada.  
  
 [Interpolación de cadenas](../../csharp/language-reference/keywords/interpolated-strings.md)  
 Puede usar expresiones de interpolación de cadenas para construir cadenas.  Una expresión de cadena interpolada es similar a una cadena de plantilla que contiene expresiones.  C\# crea una cadena reemplazando las expresiones por las representaciones ToString de los resultados de las expresiones.  Una cadena interpolada es más fácil de entender con respecto a los argumentos que el [Formatos compuestos](../Topic/Composite%20Formatting.md).  
  
 [Acceso a miembros e indexación condicional null](../../csharp/language-reference/operators/null-conditional-operators.md)  
 Puede probar si hay valores null de forma sintáctica ligera antes de realizar una operación de acceso a miembros \(`?.`\) o índice \(`?[]`\).  Estos operadores ayudan a escribir menos código para controlar las comprobaciones de null, especialmente para descender en estructuras de datos.  Si la referencia de objeto u operando izquierdo es null, la operación devuelve null.  
  
 [Literales de cadena multilínea](../../visual-basic/programming-guide/language-features/strings/string-basics.md)  
 Los literales de cadena pueden contener secuencias de nueva línea.  Ya no necesita la antigua solución alternativa que consistía en usar `<xml><![CDATA[...text with newlines...]]></xml>.Value`  
  
 Comentarios  
 Puede colocar comentarios después de las continuaciones de línea implícita, dentro de expresiones de inicializador y entre los términos de la expresión LINQ.  
  
 Resolución de nombres completos más inteligente  
 Dado código como `Threading.Thread.Sleep(1000)`, Visual Basic solía buscar el espacio de nombres "Threading", detectaba ambigüedad entre System.Threading y System.Windows.Threading y, a continuación, notificaba un error.  Ahora, Visual Basic considera juntos ambos espacios de nombres posibles.  Si aparece la lista de finalización, el editor de Visual Studio muestra los miembros de ambos tipos en la lista de finalización.  
  
 Literales de fecha con el año en primer lugar  
 Puede tener literales de fecha en el formato aaaa\-mm\-dd, `#2015-03-17 16:10 PM#`.  
  
 Propiedades de interfaz de solo lectura  
 Puede implementar propiedades de interfaz de solo lectura mediante una propiedad de lectura y escritura.  La interfaz garantiza una funcionalidad mínima y no impide que una clase de implementación pueda establecer la propiedad.  
  
 [TypeOf \<expr\> IsNot \<type\>](../../visual-basic/language-reference/operators/typeof-operator.md)  
 Para mejorar la legibilidad del código, ahora puede usar `TypeOf` con `IsNot`.  
  
 [\#Disable Warning \<ID\> y \#Enable Warning \<ID\>](../../visual-basic/language-reference/directives/directives.md)  
 Puede deshabilitar y habilitar advertencias específicas para las regiones dentro de un archivo de origen.  
  
 Mejoras de comentarios de documento XML  
 Al escribir comentarios de documento, obtiene compatibilidad inteligente de editor y compilación para validar nombres de parámetro, controlar adecuadamente `crefs` \(genéricos, operadores, etc.\), colorear y refactorizar.  
  
 [Definiciones de módulo parcial e interfaz](../../visual-basic/language-reference/modifiers/partial.md)  
 Además de clases y structs, puede declarar módulos parciales e interfaces.  
  
 [Directivas \#Region dentro de cuerpos de método](../../visual-basic/language-reference/directives/region-directive.md)  
 Puede colocar delimitadores \#Region... \#End Region en cualquier parte de un archivo, dentro de funciones e incluso abarcando los cuerpos de función.  
  
 [Las definiciones de invalidaciones son implícitamente sobrecargas](../../visual-basic/language-reference/modifiers/overrides.md)  
 Si agrega el modificador `Overrides` a una definición, el compilador agrega implícitamente `Overloads`, de modo que pueda escribir menos código en los casos comunes.  
  
 CObj permitido en argumentos de atributos  
 El compilador solía producir un error advirtiendo de que CObj\(...\) no era una constante cuando se usaba en construcciones de atributo.  
  
 Declarar y consumir métodos ambiguos de distintas interfaces  
 Anteriormente, en el código siguiente producía errores que impedían declarar `IMock` o llamar a `GetDetails` \(si estos se habían declarado en C\#\):  
  
```vb  
Interface ICustomer  
  Sub GetDetails(x As Integer)  
End Interface  
  
Interface ITime  
  Sub GetDetails(x As String)  
End Interface  
  
Interface IMock : Inherits ICustomer, ITime  
  Overloads Sub GetDetails(x As Char)  
End Interface  
  
Interface IMock2 : Inherits ICustomer, ITime  
End Interface  
  
```  
  
 Ahora el compilador usa las reglas de resolución de sobrecarga normales para elegir el `GetDetails` más apropiado que se va a llamar, y se pueden declarar relaciones de interfaz en Visual Basic como las que se muestran en el ejemplo.  
  
## Vea también  
 [Novedades de Visual Studio 2015](/visual-studio/ide/what-s-new-in-visual-studio-2015)