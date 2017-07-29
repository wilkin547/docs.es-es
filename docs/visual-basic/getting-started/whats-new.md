---
title: Novedades de Visual Basic
ms.date: 2017-04-27
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- VB.StartPage.WhatsNew
dev_langs:
- VB
helpviewer_keywords:
- new features, Visual Basic
- what's new [Visual Basic]
- Visual Basic, what's new
ms.assetid: d7e97396-7f42-4873-a81c-4ebcc4b6ca02
caps.latest.revision: 145
author: rpetrusha
ms.author: ronpet
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0a9379d5dd2d1c6b3ed6820e350c19fb346ac84c
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="whats-new-for-visual-basic"></a>Novedades de Visual Basic

En este tema se enumeran los nombres de las características clave de cada versión de Visual Basic con descripciones detalladas de las características nuevas y mejoradas de la versión más reciente del lenguaje.
  
## <a name="current-version"></a>Versión actual

Visual Basic / Visual Studio .NET 2017   
Para obtener características nuevas, vea [Visual Basic 2017](#visual-basic-2017).

## <a name="previous-versions"></a>Versiones anteriores

Visual Basic / Visual Studio .NET 2015   
Para obtener características nuevas, vea [Visual Basic 14](#visual-basic-14).

Visual Basic / Visual Studio .NET 2013  
Vistas previas de tecnología de .NET Compiler Platform ("Roslyn")

Visual Basic / Visual Studio .NET 2012   
palabras clave `Async` y `await`, iteradores, atributos de información de autor de llamada

Visual Basic / Visual Studio .NET 2010   
Propiedades autoimplementadas, inicializadores de colección, continuación de línea implícita, dinámica, covarianza/contravarianza genérica, acceso de espacio de nombres global

Visual Basic / Visual Studio .NET 2008   
Language Integrated Query (LINQ), literales XML, inferencia de tipo de variable local, inicializadores de objeto, tipos anónimos, métodos de extensión, inferencia de tipo de variable local `var`, expresiones lambda, operador `if`, métodos parciales, tipos de valor que aceptan valores null  

Visual Basic / Visual Studio .NET 2005   
El tipo `My` y tipos auxiliares (acceso a la aplicación, equipo, sistema de archivos, red)

Visual Basic / Visual Studio .NET 2003   
Operadores de desplazamiento de bits, declaración de variable de bucle

Visual Basic / Visual Studio .NET 2002   
La primera versión de Visual Basic .NET

## <a name="visual-basic-2017"></a>Visual Basic 2017

[Tuplas](../programming-guide/language-features/data-types/tuples.md)

Las tuplas son una estructura de datos ligera que se usan normalmente para devolver varios valores de una sola llamada al método. Normalmente, para devolver varios valores de un método, tiene que realizar una de las siguientes acciones:

- Definir un tipo personalizado (`Class` o `Structure`). Esta es una solución pesada.

- Definir uno o más parámetros `ByRef`, además de devolver un valor del método.
 
La compatibilidad de Visual Basic con las tuplas le permite definir rápidamente una tupla, asignar opcionalmente nombres semánticos a sus valores y recuperar sus valores rápidamente. En el ejemplo siguiente se ajusta una llamada al método <xref:System.Int32.TryParse%2A> y se devuelve una tupla.

[!code-vb[Tuple](../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

Después, puede llamar al método y controlar la tupla devuelta con código como el siguiente.

[!code-vb[ReturnTuple](../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)] 

**Literales binarios y separadores de dígitos**

Puede definir un literal binario con el prefijo `&B` o `&b`. Además, puede usar el carácter de subrayado, `_`, como un separador de dígitos para mejorar la legibilidad. En el ejemplo siguiente se usan ambas características para asignar un valor `Byte` y para mostrarlo como un número binario, hexadecimal y decimal.

[!code-vb[Binary](../../../samples/snippets/visualbasic/getting-started/bin-example.vb#1)]

Para obtener más información, vea la sección "Asignaciones literales" de los tipos de datos [Byte](../language-reference/data-types/byte-data-type.md#literal-assignments), [Integer](../language-reference/data-types/integer-data-type.md#literal-assignments), [Long](../language-reference/data-types/long-data-type.md#literal-assignments), [Short](../language-reference/data-types/short-data-type.md#literal-assignments), [SByte](../language-reference/data-types/sbyte-data-type.md#literal-assignments), [UInteger](../language-reference/data-types/uinteger-data-type.md#literal-assignments), [ULong](../language-reference/data-types/ulong-data-type.md#literal-assignments) y [UShort](../language-reference/data-types/ushort-data-type.md#literal-assignments).

**Compatibilidad con los valores devueltos de referencia de C#**

A partir de C# 7, C# admite los valores devueltos de referencia. Es decir, cuando el método de llamada recibe un valor devuelto mediante referencia, puede cambiar el valor de esta. Visual Basic no le permite crear métodos con valores devueltos de referencia, pero le permite consumirlos y modificarlos.

Por ejemplo, la siguiente clase `Sentence` escrita en C# incluye un método `FindNext` que busca la siguiente palabra de una frase que comienza por una subcadena especificada. La cadena se devuelve como un valor devuelto de referencia, y una variable `Boolean` que se ha pasado mediante referencia al método indica si la búsqueda se ha realizado correctamente. Esto significa que el autor de la llamada no solo puede leer el valor devuelto; él o ella también puede modificarlo, y esa modificación se refleja en la clase `Sentence`.

[!code-csharp[Ref-Return](../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

En su forma más sencilla, puede modificar la palabra que se ha encontrado en la frase con código como el que se muestra a continuación. Tenga en cuenta que no está asignando un valor al método, sino a la expresión que devuelve el método, que es el valor devuelto de referencia.

[!code-vb[Ref-Return](../../../samples/snippets/visualbasic/getting-started/ref-return.vb#1)]

En cambio, un problema con este código es que si no se detecta una coincidencia, el método devuelve la primera palabra. Como el ejemplo no examina el valor del argumento `Boolean` para determinar si se detecta una coincidencia, modifica la primera palabra si no hay ninguna. En el ejemplo siguiente se corrige esto reemplazando la primera palabra por ella misma si no existe ninguna coincidencia.

[!code-vb[Ref-Return](../../../samples/snippets/visualbasic/getting-started/ref-return.vb#2)]

Una solución mejor es usar un método auxiliar en el que el valor devuelto de referencia se pase mediante una referencia. El método auxiliar puede después modificar el argumento que se ha pasado por referencia. En el siguiente ejemplo se realiza esto.

[!code-vb[Ref-Return](../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

Para obtener más información, vea [Valores devueltos de referencia](../programming-guide/language-features/procedures/ref-return-values.md).

## <a name="visual-basic-14"></a>Visual Basic 14

[Nameof](../../csharp/language-reference/keywords/nameof.md)  
 Puede obtener el nombre de cadena no calificado de un tipo o miembro para usarlo en un mensaje de error sin codificar de forma rígida una cadena.  Esto permite que el código siga siendo correcto al refactorizarlo.  Esta característica también es útil para enlazar los vínculos MVC del controlador de vista de modelos y desencadenar eventos de propiedad cambiada.  
  
[Interpolación de cadenas](../../csharp/language-reference/keywords/interpolated-strings.md)  
 Puede usar expresiones de interpolación de cadenas para construir cadenas.  Una expresión de cadena interpolada es similar a una cadena de plantilla que contiene expresiones.  Una cadena interpolada es más fácil de entender con respecto a los argumentos que el [formato compuesto](../../standard/base-types/composite-format.md).  
  
[Acceso a miembros e indización condicional null](../../csharp/language-reference/operators/null-conditional-operators.md)  
Puede probar si hay valores null de forma sintáctica ligera antes de realizar una operación de acceso a miembros (`?.`) o índice (`?[]`).  Estos operadores ayudan a escribir menos código para controlar las comprobaciones de null, especialmente para descender en estructuras de datos.  Si la referencia de objeto u operando izquierdo es null, la operación devuelve null.  
  
[Literales de cadena multilínea](../../visual-basic/programming-guide/language-features/strings/string-basics.md)  
 Los literales de cadena pueden contener secuencias de nueva línea.  Ya no necesita la antigua solución alternativa que consistía en usar `<xml><![CDATA[...text with newlines...]]></xml>.Value`  
  
Comentarios  
Puede colocar comentarios después de las continuaciones de línea implícita, dentro de expresiones de inicializador y entre los términos de la expresión LINQ.  
  
 Resolución de nombres completos más inteligente  
 Dado código como `Threading.Thread.Sleep(1000)`, Visual Basic solía buscar el espacio de nombres "Threading", detectaba ambigüedad entre System.Threading y System.Windows.Threading y, a continuación, notificaba un error.  Ahora, Visual Basic considera juntos ambos espacios de nombres posibles.  Si aparece la lista de finalización, el editor de Visual Studio muestra los miembros de ambos tipos en la lista de finalización.  
  
 Literales de fecha con el año en primer lugar  
 Puede tener literales de fecha en el formato aaaa-mm-dd, `#2015-03-17 16:10 PM#`.  
  
 Propiedades de interfaz de solo lectura  
 Puede implementar propiedades de interfaz de solo lectura mediante una propiedad de lectura y escritura.  La interfaz garantiza una funcionalidad mínima y no impide que una clase de implementación pueda establecer la propiedad.  
  
 [TypeOf \<expr> IsNot \<type>](../../visual-basic/language-reference/operators/typeof-operator.md)  
 Para mejorar la legibilidad del código, ahora puede usar `TypeOf` con `IsNot`.  
  
 [#Disable Warning \<ID> y #Enable Warning \<ID>](../../visual-basic/language-reference/directives/directives.md)  
 Puede deshabilitar y habilitar advertencias específicas para las regiones dentro de un archivo de origen.  
  
 Mejoras de comentarios de documento XML  
 Al escribir comentarios de documento, obtiene compatibilidad inteligente de editor y compilación para validar nombres de parámetro, controlar adecuadamente `crefs` (genéricos, operadores, etc.), colorear y refactorizar.  
  
 [Definiciones de módulo parcial e interfaz](../../visual-basic/language-reference/modifiers/partial.md)  
 Además de clases y structs, puede declarar módulos parciales e interfaces.  
  
 [Directivas #Region dentro de cuerpos de método](../../visual-basic/language-reference/directives/region-directive.md)  
 Puede colocar delimitadores #Region... #End Region en cualquier parte de un archivo, dentro de funciones e incluso abarcando los cuerpos de función.  
  
 [Las definiciones de invalidaciones son implícitamente sobrecargas](../../visual-basic/language-reference/modifiers/overrides.md)  
 Si agrega el modificador `Overrides` a una definición, el compilador agrega implícitamente `Overloads`, de modo que pueda escribir menos código en los casos comunes.  
  
 CObj permitido en argumentos de atributos  
 El compilador solía producir un error advirtiendo de que CObj(...) no era una constante cuando se usaba en construcciones de atributo.  
  
 Declarar y consumir métodos ambiguos de distintas interfaces  
 Anteriormente, en el código siguiente producía errores que impedían declarar `IMock` o llamar a `GetDetails` (si estos se habían declarado en C#):  
  
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
  
## <a name="see-also"></a>Vea también  
 [Novedades de Visual Studio 2017](/visualstudio/ide/whats-new-in-visual-studio)

