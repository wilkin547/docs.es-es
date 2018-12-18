---
title: 'Inicialización de un diccionario con un inicializador de colección: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [C#], with Dictionary
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
ms.openlocfilehash: 42deee85b3a425531ddadfa96cfaff6d342d1221
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243886"
---
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a>Procedimientos: inicialización de un diccionario con un inicializador de colección (guía de programación de C#)

Una clase <xref:System.Collections.Generic.Dictionary%602> contiene una colección de pares clave-valor. Su método <xref:System.Collections.Generic.Dictionary%602.Add*> toma dos parámetros: uno para la clave y otro para el valor. Para inicializar <xref:System.Collections.Generic.Dictionary%602>, o cualquier otra colección cuyo método `Add` tome varios parámetros, encierre entre llaves cada uno de los conjuntos de parámetros, como se muestra en el ejemplo siguiente.

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente, <xref:System.Collections.Generic.Dictionary%602> se inicializa con instancias de tipo `StudentName`.  
  
[!code-csharp[csProgGuideLINQ#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-a-dictionary-with-a-collection-initializer_1.cs)]

Observe los dos pares de llaves en cada elemento de la colección. Las llaves internas contienen el inicializador de objeto para `StudentName`, mientras que las externas contienen el inicializador para el par clave-valor que se va a agregar a la clase <xref:System.Collections.Generic.Dictionary%602> `students`. Por último, el inicializador completo de la colección para el diccionario se encierra entre llaves.

## <a name="compiling-the-code"></a>Compilación del código

Para ejecutar este código, copie y pegue la clase en un proyecto de aplicación de la consola de Visual C# creado en Visual Studio. De manera predeterminada, el proyecto tiene como destino la versión 3.5 de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] y contiene una referencia a System.Core.dll y una directiva "using" para System.Linq. Si faltan alguno de estos requisitos del proyecto, se puede agregar manualmente.

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Inicializadores de objeto y colección](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)
