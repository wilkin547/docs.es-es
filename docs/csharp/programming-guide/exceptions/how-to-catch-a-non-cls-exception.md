---
title: Procedimiento para detectar excepciones no compatibles con CLS
description: Aprenda a detectar excepciones no compatibles con CLS. Vea un ejemplo de código y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], non-CLS
ms.assetid: db4630b3-5240-471a-b3a7-c7ff6ab31e8d
ms.openlocfilehash: db723cb1e29181e9462c5b423c66cdf8de659259
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178676"
---
# <a name="how-to-catch-a-non-cls-exception"></a>Procedimiento para detectar excepciones no compatibles con CLS

Algunos lenguajes. NET, incluido C++/CLI, permiten que los objetos inicien excepciones que no se derivan de <xref:System.Exception>. Dichas excepciones se denominan *excepciones de no compatibilidad con CLS* o *no excepciones*. En C# no se pueden producir excepciones de no compatibilidad con CLS, pero se pueden detectar de dos formas:  
  
- Dentro de un bloque `catch (RuntimeWrappedException e)`.
  
     De forma predeterminada, un ensamblado de Visual C# detecta las excepciones de no compatibilidad con CLS como excepciones ajustadas. Use este método si necesita tener acceso a la excepción original, a la que se puede tener acceso a través de la propiedad <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType>. El procedimiento mostrado más adelante en este tema explica cómo detectar las excepciones de esta manera.  
  
- Dentro de un bloque catch general (un bloque catch sin un tipo de excepción especificado) que se coloca detrás de todos los demás bloques `catch`.
  
     Use este método cuando quiera realizar alguna acción (como escribir en un archivo de registro) en respuesta a las excepciones de no compatibilidad con CLS y no necesita tener acceso a la información de excepción. De forma predeterminada, el Common Language Runtime ajusta todas las excepciones. Para deshabilitar este comportamiento, agregue este atributo de nivel de ensamblado en el código, normalmente en el archivo AssemblyInfo.cs: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.  
  
### <a name="to-catch-a-non-cls-exception"></a>Para detectar una excepción de no compatibilidad con CLS  
  
Dentro de un bloque `catch(RuntimeWrappedException e)`, se accede a la excepción original mediante la propiedad <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType>.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo detectar una excepción de no compatibilidad con CLS iniciada desde una biblioteca de clases escrita en C++/CLI. Tenga en cuenta que en este ejemplo, el código de cliente de C# conoce por adelantado que el tipo de excepción que se inicia es <xref:System.String?displayProperty=nameWithType>. Puede convertir la propiedad <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> de vuelta a su tipo original siempre que el tipo sea accesible desde su código.  
  
```csharp
// Class library written in C++/CLI.
var myClass = new ThrowNonCLS.Class1();

try
{
    // throws gcnew System::String(  
    // "I do not derive from System.Exception!");  
    myClass.TestThrow();
}
catch (RuntimeWrappedException e)
{
    String s = e.WrappedException as String;
    if (s != null)
    {
        Console.WriteLine(s);
    }
}
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Runtime.CompilerServices.RuntimeWrappedException>
- [Excepciones y control de excepciones](./index.md)
