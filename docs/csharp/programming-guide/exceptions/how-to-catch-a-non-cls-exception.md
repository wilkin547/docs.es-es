---
title: Procedimiento para detectar excepciones no compatibles con CLS
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], non-CLS
ms.assetid: db4630b3-5240-471a-b3a7-c7ff6ab31e8d
ms.openlocfilehash: 635cf0a9142f56dea4b2722fbf3f3eda505d85ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75346275"
---
# <a name="how-to-catch-a-non-cls-exception"></a><span data-ttu-id="fbc21-102">Procedimiento para detectar excepciones no compatibles con CLS</span><span class="sxs-lookup"><span data-stu-id="fbc21-102">How to catch a non-CLS exception</span></span>
<span data-ttu-id="fbc21-103">Algunos lenguajes. NET, incluido C++/CLI, permiten que los objetos inicien excepciones que no se derivan de <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="fbc21-103">Some .NET languages, including C++/CLI, allow objects to throw exceptions that do not derive from <xref:System.Exception>.</span></span> <span data-ttu-id="fbc21-104">Dichas excepciones se denominan *excepciones de no compatibilidad con CLS* o *no excepciones*.</span><span class="sxs-lookup"><span data-stu-id="fbc21-104">Such exceptions are called *non-CLS exceptions* or *non-Exceptions*.</span></span> <span data-ttu-id="fbc21-105">En C# no se pueden producir excepciones de no compatibilidad con CLS, pero se pueden detectar de dos formas:</span><span class="sxs-lookup"><span data-stu-id="fbc21-105">In C# you cannot throw non-CLS exceptions, but you can catch them in two ways:</span></span>  
  
- <span data-ttu-id="fbc21-106">Dentro de un bloque `catch (RuntimeWrappedException e)`.</span><span class="sxs-lookup"><span data-stu-id="fbc21-106">Within a `catch (RuntimeWrappedException e)` block.</span></span>
  
     <span data-ttu-id="fbc21-107">De forma predeterminada, un ensamblado de Visual C# detecta las excepciones de no compatibilidad con CLS como excepciones ajustadas.</span><span class="sxs-lookup"><span data-stu-id="fbc21-107">By default, a Visual C# assembly catches non-CLS exceptions as wrapped exceptions.</span></span> <span data-ttu-id="fbc21-108">Use este método si necesita tener acceso a la excepción original, a la que se puede tener acceso a través de la propiedad <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fbc21-108">Use this method if you need access to the original exception, which can be accessed through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="fbc21-109">El procedimiento mostrado más adelante en este tema explica cómo detectar las excepciones de esta manera.</span><span class="sxs-lookup"><span data-stu-id="fbc21-109">The procedure later in this topic explains how to catch exceptions in this manner.</span></span>  
  
- <span data-ttu-id="fbc21-110">Dentro de un bloque catch general (un bloque catch sin un tipo de excepción especificado) que se coloca detrás de todos los demás bloques `catch`.</span><span class="sxs-lookup"><span data-stu-id="fbc21-110">Within a general catch block (a catch block without an exception type specified) that is put after all other `catch` blocks.</span></span>
  
     <span data-ttu-id="fbc21-111">Use este método cuando quiera realizar alguna acción (como escribir en un archivo de registro) en respuesta a las excepciones de no compatibilidad con CLS y no necesita tener acceso a la información de excepción.</span><span class="sxs-lookup"><span data-stu-id="fbc21-111">Use this method when you want to perform some action (such as writing to a log file) in response to non-CLS exceptions, and you do not need access to the exception information.</span></span> <span data-ttu-id="fbc21-112">De forma predeterminada, el Common Language Runtime ajusta todas las excepciones.</span><span class="sxs-lookup"><span data-stu-id="fbc21-112">By default the common language runtime wraps all exceptions.</span></span> <span data-ttu-id="fbc21-113">Para deshabilitar este comportamiento, agregue este atributo de nivel de ensamblado en el código, normalmente en el archivo AssemblyInfo.cs: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.</span><span class="sxs-lookup"><span data-stu-id="fbc21-113">To disable this behavior, add this assembly-level attribute to your code, typically in the AssemblyInfo.cs file: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.</span></span>  
  
### <a name="to-catch-a-non-cls-exception"></a><span data-ttu-id="fbc21-114">Para detectar una excepción de no compatibilidad con CLS</span><span class="sxs-lookup"><span data-stu-id="fbc21-114">To catch a non-CLS exception</span></span>  
  
<span data-ttu-id="fbc21-115">Dentro de un bloque `catch(RuntimeWrappedException e)`, se accede a la excepción original mediante la propiedad <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fbc21-115">Within a `catch(RuntimeWrappedException e)` block, access the original exception through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbc21-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fbc21-116">Example</span></span>  
 <span data-ttu-id="fbc21-117">En el ejemplo siguiente se muestra cómo detectar una excepción de no compatibilidad con CLS iniciada desde una biblioteca de clases escrita en C++/CLI.</span><span class="sxs-lookup"><span data-stu-id="fbc21-117">The following example shows how to catch a non-CLS exception that was thrown from a class library written in C++/CLI.</span></span> <span data-ttu-id="fbc21-118">Tenga en cuenta que en este ejemplo, el código de cliente de C# conoce por adelantado que el tipo de excepción que se inicia es <xref:System.String?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fbc21-118">Note that in this example, the C# client code knows in advance that the exception type being thrown is a <xref:System.String?displayProperty=nameWithType>.</span></span> <span data-ttu-id="fbc21-119">Puede convertir la propiedad <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> de vuelta a su tipo original siempre que el tipo sea accesible desde su código.</span><span class="sxs-lookup"><span data-stu-id="fbc21-119">You can cast the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property back its original type as long as that type is accessible from your code.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fbc21-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="fbc21-120">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeWrappedException>
- [<span data-ttu-id="fbc21-121">Excepciones y control de excepciones</span><span class="sxs-lookup"><span data-stu-id="fbc21-121">Exceptions and Exception Handling</span></span>](./index.md)
