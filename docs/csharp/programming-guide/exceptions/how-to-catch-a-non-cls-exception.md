---
title: "C&#243;mo: Detectar excepciones no compatibles con CLS | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "excepciones [C#], no conformes a CLS"
ms.assetid: db4630b3-5240-471a-b3a7-c7ff6ab31e8d
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# C&#243;mo: Detectar excepciones no compatibles con CLS
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Algunos lenguajes de .NET, incluido C\+\+\/CLI, permiten que los objetos inicien excepciones que no se derivan de <xref:System.Exception>.  Tales excepciones se denominan *excepciones que no son CLS* o *no excepciones*.  En [!INCLUDE[csprcs](../../../csharp/includes/csprcs_md.md)] no puede iniciar excepciones que no son CLS, pero puede detectarlas de dos maneras:  
  
-   Dentro de un bloque `catch (Exception e)` como <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.  
  
     De forma predeterminada, un ensamblado [!INCLUDE[csprcs](../../../csharp/includes/csprcs_md.md)] detecta las excepciones que no son CLS como excepciones ajustadas.  Utilice este método si necesita obtener acceso a la excepción original, lo cual se hace a través de la propiedad <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A>.  El procedimiento posterior de este tema explica cómo detectar excepciones de este modo.  
  
-   Dentro de un bloque catch general \(un bloque catch sin un tipo de excepción especificado\) colocado detrás de un bloque `catch (Exception)` o `catch (Exception e)`.  
  
     Utilice este método si desea realizar alguna acción \(como escribir en un archivo de registro\) en respuesta a las excepciones que no son CLS y no necesita obtener acceso a la información de excepción.  De forma predeterminada, Common Language Runtime ajusta todas las excepciones.  Para deshabilitar este comportamiento, agregue este atributo del nivel de ensamblado al código, normalmente en el archivo AssemblyInfo.cs: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.  
  
### Para detectar una excepción que no es CLS  
  
1.  Dentro de `catch(Exception e) block`, utilice la palabra clave `as` para comprobar si `e` se puede convertir en <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.  
  
2.  Obtenga acceso a la excepción original a través de la propiedad <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A>.  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo detectar una excepción que no es CLS iniciada desde una biblioteca de clases escrita en C\+\+\/CLR.  Tenga en cuenta que, en este ejemplo, el código de cliente [!INCLUDE[csprcs](../../../csharp/includes/csprcs_md.md)] sabe de antemano que el tipo de excepción que se va a iniciar es <xref:System.String?displayProperty=fullName>.  Puede volver a convertir la propiedad <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> en su tipo original siempre que ese tipo sea accesible desde el código.  
  
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
  
## Vea también  
 <xref:System.Runtime.CompilerServices.RuntimeWrappedException>   
 [Excepciones y control de excepciones](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md)