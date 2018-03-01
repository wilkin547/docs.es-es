---
title: "Cómo: Detectar excepciones no compatibles con CLS"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- exceptions [C#], non-CLS
ms.assetid: db4630b3-5240-471a-b3a7-c7ff6ab31e8d
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 473cace033983915c66647d14cae16dc7f5d5b9d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-catch-a-non-cls-exception"></a>Cómo: Detectar excepciones no compatibles con CLS
Algunos lenguajes. NET, incluido C++/CLI, permiten que los objetos inicien excepciones que no se derivan de <xref:System.Exception>. Dichas excepciones se denominan *excepciones de no compatibilidad con CLS* o *no excepciones*. En [!INCLUDE[csprcs](~/includes/csprcs-md.md)] no se pueden producir excepciones de no compatibilidad con CLS, pero se pueden detectar de dos formas:  
  
-   Dentro de un bloque `catch (Exception e)` como <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.  
  
     De forma predeterminada, un ensamblado de [!INCLUDE[csprcs](~/includes/csprcs-md.md)] detecta las excepciones de no compatibilidad con CLS como excepciones ajustadas. Use este método si necesita tener acceso a la excepción original, a la que se puede tener acceso a través de la propiedad <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A>. El procedimiento mostrado más adelante en este tema explica cómo detectar las excepciones de esta manera.  
  
-   Dentro de un bloque catch general (un bloque catch sin un tipo de excepción especificado) que se coloca detrás de un bloque `catch (Exception)` o `catch (Exception e)`.  
  
     Use este método cuando quiera realizar alguna acción (como escribir en un archivo de registro) en respuesta a las excepciones de no compatibilidad con CLS y no necesita tener acceso a la información de excepción. De forma predeterminada, el Common Language Runtime ajusta todas las excepciones. Para deshabilitar este comportamiento, agregue este atributo de nivel de ensamblado en el código, normalmente en el archivo AssemblyInfo.cs: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.  
  
### <a name="to-catch-a-non-cls-exception"></a>Para detectar una excepción de no compatibilidad con CLS  
  
1.  Dentro de `catch(Exception e) block`, use la palabra clave `as` para probar si `e` puede convertirse en <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.  
  
2.  Acceda a la excepción original mediante la propiedad <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo detectar una excepción de no compatibilidad con CLS iniciada desde una biblioteca de clases escrita en C++/CLR. Tenga en cuenta que en este ejemplo, el código de cliente de [!INCLUDE[csprcs](~/includes/csprcs-md.md)] conoce por adelantado que el tipo de excepción producida es un <xref:System.String?displayProperty=nameWithType>. Puede convertir la propiedad <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> de vuelta a su tipo original siempre que el tipo sea accesible desde su código.  
  
```  
// Class library written in C++/CLR.  
   ThrowNonCLS.Class1 myClass = new ThrowNonCLS.Class1();  
  
   try  
   {  
    // throws gcnew System::String(  
    // "I do not derive from System.Exception!");  
    myClass.TestThrow();   
   }  
  
   catch (Exception e)  
   {  
    RuntimeWrappedException rwe = e as RuntimeWrappedException;  
    if (rwe != null)      
    {  
      String s = rwe.WrappedException as String;  
      if (s != null)  
      {  
        Console.WriteLine(s);  
      }  
    }  
    else  
    {  
       // Handle other System.Exception types.  
    }  
   }             
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.CompilerServices.RuntimeWrappedException>  
 [Excepciones y control de excepciones](../../../csharp/programming-guide/exceptions/index.md)
