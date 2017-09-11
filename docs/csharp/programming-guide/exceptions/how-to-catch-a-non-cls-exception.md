---
title: "Cómo: Detectar excepciones no compatibles con CLS"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- exceptions [C#], non-CLS
ms.assetid: db4630b3-5240-471a-b3a7-c7ff6ab31e8d
caps.latest.revision: 8
author: BillWagner
ms.author: wiwagn
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
ms.openlocfilehash: 18a19fe34b8ec13bd9fc6d25335d0931a22ce4a3
ms.contentlocale: es-es
ms.lasthandoff: 09/08/2017

---
# <a name="how-to-catch-a-non-cls-exception"></a><span data-ttu-id="4320e-102">Cómo: Detectar excepciones no compatibles con CLS</span><span class="sxs-lookup"><span data-stu-id="4320e-102">How to: Catch a non-CLS Exception</span></span>
<span data-ttu-id="4320e-103">Algunos lenguajes. NET, incluido C++/CLI, permiten que los objetos inicien excepciones que no se derivan de <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="4320e-103">Some .NET languages, including C++/CLI, allow objects to throw exceptions that do not derive from <xref:System.Exception>.</span></span> <span data-ttu-id="4320e-104">Dichas excepciones se denominan *excepciones de no compatibilidad con CLS* o *no excepciones*.</span><span class="sxs-lookup"><span data-stu-id="4320e-104">Such exceptions are called *non-CLS exceptions* or *non-Exceptions*.</span></span> <span data-ttu-id="4320e-105">En [!INCLUDE[csprcs](~/includes/csprcs-md.md)] no se pueden producir excepciones de no compatibilidad con CLS, pero se pueden detectar de dos formas:</span><span class="sxs-lookup"><span data-stu-id="4320e-105">In [!INCLUDE[csprcs](~/includes/csprcs-md.md)] you cannot throw non-CLS exceptions, but you can catch them in two ways:</span></span>  
  
-   <span data-ttu-id="4320e-106">Dentro de un bloque `catch (Exception e)` como <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.</span><span class="sxs-lookup"><span data-stu-id="4320e-106">Within a `catch (Exception e)` block as a <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.</span></span>  
  
     <span data-ttu-id="4320e-107">De forma predeterminada, un ensamblado de [!INCLUDE[csprcs](~/includes/csprcs-md.md)] detecta las excepciones de no compatibilidad con CLS como excepciones ajustadas.</span><span class="sxs-lookup"><span data-stu-id="4320e-107">By default, a [!INCLUDE[csprcs](~/includes/csprcs-md.md)] assembly catches non-CLS exceptions as wrapped exceptions.</span></span> <span data-ttu-id="4320e-108">Use este método si necesita tener acceso a la excepción original, a la que se puede tener acceso a través de la propiedad <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A>.</span><span class="sxs-lookup"><span data-stu-id="4320e-108">Use this method if you need access to the original exception, which can be accessed through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> property.</span></span> <span data-ttu-id="4320e-109">El procedimiento mostrado más adelante en este tema explica cómo detectar las excepciones de esta manera.</span><span class="sxs-lookup"><span data-stu-id="4320e-109">The procedure later in this topic explains how to catch exceptions in this manner.</span></span>  
  
-   <span data-ttu-id="4320e-110">Dentro de un bloque catch general (un bloque catch sin un tipo de excepción especificado) que se coloca detrás de un bloque `catch (Exception)` o `catch (Exception e)`.</span><span class="sxs-lookup"><span data-stu-id="4320e-110">Within a general catch block (a catch block without an exception type specified) that is put after a `catch (Exception)` or `catch (Exception e)` block.</span></span>  
  
     <span data-ttu-id="4320e-111">Use este método cuando quiera realizar alguna acción (como escribir en un archivo de registro) en respuesta a las excepciones de no compatibilidad con CLS y no necesita tener acceso a la información de excepción.</span><span class="sxs-lookup"><span data-stu-id="4320e-111">Use this method when you want to perform some action (such as writing to a log file) in response to non-CLS exceptions, and you do not need access to the exception information.</span></span> <span data-ttu-id="4320e-112">De forma predeterminada, el Common Language Runtime ajusta todas las excepciones.</span><span class="sxs-lookup"><span data-stu-id="4320e-112">By default the common language runtime wraps all exceptions.</span></span> <span data-ttu-id="4320e-113">Para deshabilitar este comportamiento, agregue este atributo de nivel de ensamblado en el código, normalmente en el archivo AssemblyInfo.cs: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.</span><span class="sxs-lookup"><span data-stu-id="4320e-113">To disable this behavior, add this assembly-level attribute to your code, typically in the AssemblyInfo.cs file: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.</span></span>  
  
### <a name="to-catch-a-non-cls-exception"></a><span data-ttu-id="4320e-114">Para detectar una excepción de no compatibilidad con CLS</span><span class="sxs-lookup"><span data-stu-id="4320e-114">To catch a non-CLS exception</span></span>  
  
1.  <span data-ttu-id="4320e-115">Dentro de `catch(Exception e) block`, use la palabra clave `as` para probar si `e` puede convertirse en <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.</span><span class="sxs-lookup"><span data-stu-id="4320e-115">Within a `catch(Exception e) block`, use the `as` keyword to test whether `e` can be cast to a <xref:System.Runtime.CompilerServices.RuntimeWrappedException>.</span></span>  
  
2.  <span data-ttu-id="4320e-116">Acceda a la excepción original mediante la propiedad <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A>.</span><span class="sxs-lookup"><span data-stu-id="4320e-116">Access the original exception through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4320e-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4320e-117">Example</span></span>  
 <span data-ttu-id="4320e-118">En el ejemplo siguiente se muestra cómo detectar una excepción de no compatibilidad con CLS iniciada desde una biblioteca de clases escrita en C++/CLR.</span><span class="sxs-lookup"><span data-stu-id="4320e-118">The following example shows how to catch a non-CLS exception that was thrown from a class library written in C++/CLR.</span></span> <span data-ttu-id="4320e-119">Tenga en cuenta que en este ejemplo, el código de cliente de [!INCLUDE[csprcs](~/includes/csprcs-md.md)] conoce por adelantado que el tipo de excepción producida es un <xref:System.String?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="4320e-119">Note that in this example, the [!INCLUDE[csprcs](~/includes/csprcs-md.md)] client code knows in advance that the exception type being thrown is a <xref:System.String?displayProperty=fullName>.</span></span> <span data-ttu-id="4320e-120">Puede convertir la propiedad <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> de vuelta a su tipo original siempre que el tipo sea accesible desde su código.</span><span class="sxs-lookup"><span data-stu-id="4320e-120">You can cast the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A> property back its original type as long as that type is accessible from your code.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4320e-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="4320e-121">See Also</span></span>  
 <span data-ttu-id="4320e-122"><xref:System.Runtime.CompilerServices.RuntimeWrappedException></span><span class="sxs-lookup"><span data-stu-id="4320e-122"><xref:System.Runtime.CompilerServices.RuntimeWrappedException></span></span>   
 [<span data-ttu-id="4320e-123">Excepciones y control de excepciones</span><span class="sxs-lookup"><span data-stu-id="4320e-123">Exceptions and Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/index.md)

