---
title: Procedimiento para detectar excepciones no compatibles con CLS
description: Aprenda a detectar excepciones no compatibles con CLS. Vea un ejemplo de código y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], non-CLS
ms.assetid: db4630b3-5240-471a-b3a7-c7ff6ab31e8d
ms.openlocfilehash: 255de4cab9a72491eb3b9624d968539d432e0442
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302014"
---
# <a name="how-to-catch-a-non-cls-exception"></a><span data-ttu-id="edcbf-104">Procedimiento para detectar excepciones no compatibles con CLS</span><span class="sxs-lookup"><span data-stu-id="edcbf-104">How to catch a non-CLS exception</span></span>
<span data-ttu-id="edcbf-105">Algunos lenguajes. NET, incluido C++/CLI, permiten que los objetos inicien excepciones que no se derivan de <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="edcbf-105">Some .NET languages, including C++/CLI, allow objects to throw exceptions that do not derive from <xref:System.Exception>.</span></span> <span data-ttu-id="edcbf-106">Dichas excepciones se denominan *excepciones de no compatibilidad con CLS* o *no excepciones*.</span><span class="sxs-lookup"><span data-stu-id="edcbf-106">Such exceptions are called *non-CLS exceptions* or *non-Exceptions*.</span></span> <span data-ttu-id="edcbf-107">En C# no se pueden producir excepciones de no compatibilidad con CLS, pero se pueden detectar de dos formas:</span><span class="sxs-lookup"><span data-stu-id="edcbf-107">In C# you cannot throw non-CLS exceptions, but you can catch them in two ways:</span></span>  
  
- <span data-ttu-id="edcbf-108">Dentro de un bloque `catch (RuntimeWrappedException e)`.</span><span class="sxs-lookup"><span data-stu-id="edcbf-108">Within a `catch (RuntimeWrappedException e)` block.</span></span>
  
     <span data-ttu-id="edcbf-109">De forma predeterminada, un ensamblado de Visual C# detecta las excepciones de no compatibilidad con CLS como excepciones ajustadas.</span><span class="sxs-lookup"><span data-stu-id="edcbf-109">By default, a Visual C# assembly catches non-CLS exceptions as wrapped exceptions.</span></span> <span data-ttu-id="edcbf-110">Use este método si necesita tener acceso a la excepción original, a la que se puede tener acceso a través de la propiedad <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="edcbf-110">Use this method if you need access to the original exception, which can be accessed through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="edcbf-111">El procedimiento mostrado más adelante en este tema explica cómo detectar las excepciones de esta manera.</span><span class="sxs-lookup"><span data-stu-id="edcbf-111">The procedure later in this topic explains how to catch exceptions in this manner.</span></span>  
  
- <span data-ttu-id="edcbf-112">Dentro de un bloque catch general (un bloque catch sin un tipo de excepción especificado) que se coloca detrás de todos los demás bloques `catch`.</span><span class="sxs-lookup"><span data-stu-id="edcbf-112">Within a general catch block (a catch block without an exception type specified) that is put after all other `catch` blocks.</span></span>
  
     <span data-ttu-id="edcbf-113">Use este método cuando quiera realizar alguna acción (como escribir en un archivo de registro) en respuesta a las excepciones de no compatibilidad con CLS y no necesita tener acceso a la información de excepción.</span><span class="sxs-lookup"><span data-stu-id="edcbf-113">Use this method when you want to perform some action (such as writing to a log file) in response to non-CLS exceptions, and you do not need access to the exception information.</span></span> <span data-ttu-id="edcbf-114">De forma predeterminada, el Common Language Runtime ajusta todas las excepciones.</span><span class="sxs-lookup"><span data-stu-id="edcbf-114">By default the common language runtime wraps all exceptions.</span></span> <span data-ttu-id="edcbf-115">Para deshabilitar este comportamiento, agregue este atributo de nivel de ensamblado en el código, normalmente en el archivo AssemblyInfo.cs: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.</span><span class="sxs-lookup"><span data-stu-id="edcbf-115">To disable this behavior, add this assembly-level attribute to your code, typically in the AssemblyInfo.cs file: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.</span></span>  
  
### <a name="to-catch-a-non-cls-exception"></a><span data-ttu-id="edcbf-116">Para detectar una excepción de no compatibilidad con CLS</span><span class="sxs-lookup"><span data-stu-id="edcbf-116">To catch a non-CLS exception</span></span>  
  
<span data-ttu-id="edcbf-117">Dentro de un bloque `catch(RuntimeWrappedException e)`, se accede a la excepción original mediante la propiedad <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="edcbf-117">Within a `catch(RuntimeWrappedException e)` block, access the original exception through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="edcbf-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="edcbf-118">Example</span></span>  
 <span data-ttu-id="edcbf-119">En el ejemplo siguiente se muestra cómo detectar una excepción de no compatibilidad con CLS iniciada desde una biblioteca de clases escrita en C++/CLI.</span><span class="sxs-lookup"><span data-stu-id="edcbf-119">The following example shows how to catch a non-CLS exception that was thrown from a class library written in C++/CLI.</span></span> <span data-ttu-id="edcbf-120">Tenga en cuenta que en este ejemplo, el código de cliente de C# conoce por adelantado que el tipo de excepción que se inicia es <xref:System.String?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="edcbf-120">Note that in this example, the C# client code knows in advance that the exception type being thrown is a <xref:System.String?displayProperty=nameWithType>.</span></span> <span data-ttu-id="edcbf-121">Puede convertir la propiedad <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> de vuelta a su tipo original siempre que el tipo sea accesible desde su código.</span><span class="sxs-lookup"><span data-stu-id="edcbf-121">You can cast the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property back its original type as long as that type is accessible from your code.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="edcbf-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="edcbf-122">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeWrappedException>
- [<span data-ttu-id="edcbf-123">Excepciones y control de excepciones</span><span class="sxs-lookup"><span data-stu-id="edcbf-123">Exceptions and Exception Handling</span></span>](./index.md)
