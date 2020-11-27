---
title: Excepciones de tiempo de ejecución en las aplicaciones nativas de .NET
ms.date: 03/30/2017
ms.assetid: 5f050181-8fdd-4a4e-9d16-f84c22a88a97
ms.openlocfilehash: 5c521eed94590e583a761cc2003460875e690fa9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96287857"
---
# <a name="runtime-exceptions-in-net-native-apps"></a><span data-ttu-id="19998-102">Excepciones de tiempo de ejecución en las aplicaciones nativas de .NET</span><span class="sxs-lookup"><span data-stu-id="19998-102">Runtime Exceptions in .NET Native Apps</span></span>

<span data-ttu-id="19998-103">Es importante probar las versiones de lanzamiento de la aplicación de la Plataforma universal de Windows en las plataformas de destino, ya que las configuraciones de depuración y de lanzamiento son completamente diferentes.</span><span class="sxs-lookup"><span data-stu-id="19998-103">It is important to test the release builds of your Universal Windows Platform app on their target platforms because the debug and release configurations are completely different.</span></span> <span data-ttu-id="19998-104">De forma predeterminada, la configuración de depuración utiliza el tiempo de ejecución de .NET Core para compilar la aplicación, pero la configuración de lanzamiento usa .NET Native para compilar la aplicación en código nativo.</span><span class="sxs-lookup"><span data-stu-id="19998-104">By default, the debug configuration uses the .NET Core runtime to compile your app, but the release configuration uses .NET Native to compile your app to native code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="19998-105">Para obtener información sobre cómo tratar las excepciones [MissingMetadataException](missingmetadataexception-class-net-native.md), [MissingInteropDataException](missinginteropdataexception-class-net-native.md)y [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) que se pueden encontrar al probar las versiones de lanzamiento de la aplicación, vea "paso 4: resolver manualmente los metadatos que faltan: en el tema [Introducción](getting-started-with-net-native.md) , así como la referencia de archivos de configuración de [Reflection y .net Native](reflection-and-net-native.md) y [directivas de tiempo de ejecución (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md).</span><span class="sxs-lookup"><span data-stu-id="19998-105">For information on dealing with the [MissingMetadataException](missingmetadataexception-class-net-native.md), [MissingInteropDataException](missinginteropdataexception-class-net-native.md), and [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) exceptions that you may encounter when testing the release versions of your app, see "Step 4: Manually resolve missing metadata: in the [Getting Started](getting-started-with-net-native.md) topic, as well as [Reflection and .NET Native](reflection-and-net-native.md) and [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md).</span></span>  
  
## <a name="debug-and-release-builds"></a><span data-ttu-id="19998-106">Compilaciones de depuración y de lanzamiento</span><span class="sxs-lookup"><span data-stu-id="19998-106">Debug and release builds</span></span>  

 <span data-ttu-id="19998-107">Cuando se ejecuta la compilación de depuración en el tiempo de ejecución de .NET Core, no se ha compilado en código nativo.</span><span class="sxs-lookup"><span data-stu-id="19998-107">When the debug build executes against the .NET Core runtime, it has not been compiled to native code.</span></span> <span data-ttu-id="19998-108">Esto hace que todos los servicios que normalmente ofrece el tiempo de ejecución estén disponibles para su aplicación.</span><span class="sxs-lookup"><span data-stu-id="19998-108">This makes all of the services ordinarily provided by the runtime available to your app.</span></span>  
  
 <span data-ttu-id="19998-109">Por otro lado, la compilación de lanzamiento compila a código nativo para las plataformas de destino, quita la mayoría de dependencias de bibliotecas y tiempos de ejecución externos y optimiza enormemente el código para obtener el máximo rendimiento.</span><span class="sxs-lookup"><span data-stu-id="19998-109">On the other hand, the release build compiles to native code for its target platforms, removes most dependencies on external runtimes and libraries, and heavily optimizes code for maximum performance.</span></span>  
  
 <span data-ttu-id="19998-110">Cuando se depuran compilaciones de lanzamiento que se compilaron con .NET Native:</span><span class="sxs-lookup"><span data-stu-id="19998-110">When you debug release builds that are compiled by using .NET Native:</span></span>  
  
- <span data-ttu-id="19998-111">Use el motor de depuración de .NET Native, que es diferente de las herramientas de depuración de .NET normal.</span><span class="sxs-lookup"><span data-stu-id="19998-111">You use the .NET Native debug engine, which is different from the normal .NET debugging tools.</span></span>  
  
- <span data-ttu-id="19998-112">El tamaño de su archivo ejecutable se reduce tanto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="19998-112">The size of your executable is reduced as much as possible.</span></span> <span data-ttu-id="19998-113">Una de las formas en que .NET Native reduce el tamaño de un archivo ejecutable es recortando considerablemente los mensajes de excepción en tiempo de ejecución, un tema que se explica con más detalle en la sección [Runtime exception messages](#Messages) .</span><span class="sxs-lookup"><span data-stu-id="19998-113">One of the ways that .NET Native reduces the size of an executable is by significantly trimming runtime exception messages, a topic discussed in greater detail in the [Runtime exception messages](#Messages) section.</span></span>  
  
- <span data-ttu-id="19998-114">El código está altamente optimizado.</span><span class="sxs-lookup"><span data-stu-id="19998-114">Your code is heavily optimized.</span></span> <span data-ttu-id="19998-115">Esto significa que la inserción se utiliza siempre que es posible.</span><span class="sxs-lookup"><span data-stu-id="19998-115">This means that inlining is used whenever possible.</span></span> <span data-ttu-id="19998-116">(La inclusión mueve el código de las rutinas externas a la rutina de llamada).   El hecho de que .NET Native proporciona un entorno en tiempo de ejecución especializado e implementa la inclusión agresiva afecta a la pila de llamadas que se muestra al depurar.</span><span class="sxs-lookup"><span data-stu-id="19998-116">(Inlining moves code from external routines into the calling routine.)   The fact that .NET Native provides a specialized runtime and implements aggressive inlining  affects the call stack that is displayed when debugging.</span></span>  <span data-ttu-id="19998-117">Para más información, consulte la sección [Runtime call stack](#CallStack) .</span><span class="sxs-lookup"><span data-stu-id="19998-117">For more information, see the [Runtime call stack](#CallStack) section.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="19998-118">Puede controlar si las compilaciones de depuración y de lanzamiento se compilan con la cadena de herramientas de .NET Native mediante la activación o desactivación del cuadro **Compilar con cadena de herramientas de .NET Native** .</span><span class="sxs-lookup"><span data-stu-id="19998-118">You can control whether the debug and release builds are compiled with the .NET Native tool chain by checking or unchecking the **Compile with .NET Native tool chain** box.</span></span>   <span data-ttu-id="19998-119">Sin embargo, tenga en cuenta que la Tienda Windows siempre compilará la versión de producción de la aplicación con la cadena de herramientas de .NET Native.</span><span class="sxs-lookup"><span data-stu-id="19998-119">Note, however, that the Windows Store will always compile the production version of your app with the .NET Native tool chain.</span></span>  
  
<a name="Messages"></a>

## <a name="runtime-exception-messages"></a><span data-ttu-id="19998-120">Runtime exception messages</span><span class="sxs-lookup"><span data-stu-id="19998-120">Runtime exception messages</span></span>  

 <span data-ttu-id="19998-121">Para minimizar el tamaño del archivo ejecutable de la aplicación, .NET Native no incluye el texto completo de los mensajes de excepción.</span><span class="sxs-lookup"><span data-stu-id="19998-121">To minimize application executable size, .NET Native does not include the full text of exception messages.</span></span> <span data-ttu-id="19998-122">Como resultado, puede que las excepciones de tiempo de ejecución en las compilaciones de lanzamiento no muestren el texto completo de los mensajes de excepción.</span><span class="sxs-lookup"><span data-stu-id="19998-122">As a result, runtime exceptions thrown in release builds may not display the full text of exception messages.</span></span> <span data-ttu-id="19998-123">En su lugar, el texto puede constar de una subcadena junto con un vínculo para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="19998-123">Instead, the text may consist of a substring along with a link to follow for more information.</span></span> <span data-ttu-id="19998-124">Por ejemplo, la información de excepción puede aparecer como:</span><span class="sxs-lookup"><span data-stu-id="19998-124">For example, the exception information may appear as:</span></span>  
  
```output
Exception thrown: '$16_System.AggregateException' in Unknown Module.  
  
Additional information: AggregateException_ctor_DefaultMessage  
  
If there is a handler for this exception, the program may be safely continued.  
```  
  
 <span data-ttu-id="19998-125">Si necesita el mensaje de excepción completo, ejecute en su lugar la versión de depuración.</span><span class="sxs-lookup"><span data-stu-id="19998-125">If you need the complete exception message,  run the debug build instead.</span></span> <span data-ttu-id="19998-126">Por ejemplo, la información de excepción anterior de la compilación de lanzamiento puede aparecer en la compilación de depuración como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="19998-126">For example, the previous exception information  from the release build might appear as follows in the debug build:</span></span>  
  
```output
Exception thrown: 'System.AggregateException' in NativeApp.exe.  
  
Additional information: Value does not fall within the expected range.  
```  
  
<a name="CallStack"></a>

## <a name="runtime-call-stack"></a><span data-ttu-id="19998-127">Runtime call stack</span><span class="sxs-lookup"><span data-stu-id="19998-127">Runtime call stack</span></span>  

 <span data-ttu-id="19998-128">Debido a la inserción y a otras optimizaciones, puede que la pila de llamadas que muestra una aplicación compilada con la cadena de herramientas de .NET Native no le ayude a identificar claramente la ruta de acceso a una excepción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="19998-128">Because of inlining and other optimizations, the call stack displayed by an app compiled by the .NET Native tool chain may not help you to  clearly identify the path to a runtime exception.</span></span>  
  
 <span data-ttu-id="19998-129">Para obtener la pila completa, ejecute la compilación de depuración en su lugar.</span><span class="sxs-lookup"><span data-stu-id="19998-129">To get the full stack, run the debug build instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19998-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="19998-130">See also</span></span>

- [<span data-ttu-id="19998-131">Depuración de aplicaciones universales de Windows de .NET Native</span><span class="sxs-lookup"><span data-stu-id="19998-131">Debugging .NET Native Windows Universal Apps</span></span>](https://devblogs.microsoft.com/devops/debugging-net-native-windows-universal-apps/)
- [<span data-ttu-id="19998-132">Introducción</span><span class="sxs-lookup"><span data-stu-id="19998-132">Getting Started</span></span>](getting-started-with-net-native.md)
