---
title: 'Mitigación: Nuevo compilador JIT de 64 bits'
description: Obtenga información sobre el nuevo compilador JIT de 64 bits incluido en .NET Framework 4.6, así como el comportamiento inesperado o las excepciones que pueden producirse durante la compilación.
ms.date: 03/30/2017
helpviewer_keywords:
- JIT compiler, 64-bit
- JIT compilation, 64-bit
- RyuJIT compiler
ms.assetid: 0332dabc-72c5-4bdc-8975-20d717802b17
ms.openlocfilehash: 228c286f6c5620dc838df5002edc60863a0fe4e2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256604"
---
# <a name="mitigation-new-64-bit-jit-compiler"></a><span data-ttu-id="b798b-103">Mitigación: Nuevo compilador JIT de 64 bits</span><span class="sxs-lookup"><span data-stu-id="b798b-103">Mitigation: New 64-bit JIT Compiler</span></span>

<span data-ttu-id="b798b-104">A partir de .NET Framework 4.6, el entorno de ejecución incluye un nuevo compilador JIT de 64 bits para la compilación Just-In-Time.</span><span class="sxs-lookup"><span data-stu-id="b798b-104">Starting with .NET Framework 4.6, the runtime includes a new 64-bit JIT compiler for just-in-time compilation.</span></span> <span data-ttu-id="b798b-105">Este cambio no afecta a la compilación con el compilador JIT de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="b798b-105">This change does not affect compilation with the 32-bit JIT compiler.</span></span>  
  
## <a name="unexpected-behavior-or-exceptions"></a><span data-ttu-id="b798b-106">Comportamiento inesperado o excepciones</span><span class="sxs-lookup"><span data-stu-id="b798b-106">Unexpected behavior or exceptions</span></span>  

 <span data-ttu-id="b798b-107">En algunos casos, la compilación con el nuevo compilador JIT de 64 bits provoca una excepción en tiempo de ejecución o en el comportamiento que no se observa al ejecutar el código compilado por el compilador JIT de 64 bits antiguo.</span><span class="sxs-lookup"><span data-stu-id="b798b-107">In some cases, compilation with the new 64-bit JIT compiler results in a runtime exception or in behavior that is not observed when executing code compiled by the older 64-bit JIT compiler.</span></span> <span data-ttu-id="b798b-108">Las diferencias conocidas incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b798b-108">The known differences include the following:</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b798b-109">Todos estos problemas conocidos se han solucionado en el nuevo compilador de 64 bits publicado con .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="b798b-109">All of these known issues have been addressed in the new 64-bit compiler released with the .NET Framework 4.6.2.</span></span> <span data-ttu-id="b798b-110">También se han abordado la mayoría en las versiones de servicio de .NET Framework 4.6 y 4.6.1 que se incluyen con Windows Update.</span><span class="sxs-lookup"><span data-stu-id="b798b-110">Most have also been addressed in service releases of the .NET Framework 4.6 and 4.6.1 that are included with Windows Update.</span></span> <span data-ttu-id="b798b-111">Puede eliminar estos problemas asegurándose de que la versión de Windows está actualizada o actualizando a .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="b798b-111">You can eliminate these issues by ensuring that your version of Windows is up to date, or by upgrading to the .NET Framework 4.6.2.</span></span>  
  
- <span data-ttu-id="b798b-112">En determinadas condiciones, una operación de conversión unboxing puede producir una <xref:System.NullReferenceException> en versiones de lanzamiento con la optimización activada.</span><span class="sxs-lookup"><span data-stu-id="b798b-112">Under certain conditions, an unboxing operation may throw a <xref:System.NullReferenceException> in Release builds with optimization turned on.</span></span>  
  
- <span data-ttu-id="b798b-113">En algunos casos, la ejecución del código de producción en un cuerpo del método de gran tamaño puede producir una <xref:System.StackOverflowException>.</span><span class="sxs-lookup"><span data-stu-id="b798b-113">In some cases, execution of production code in a large method body may throw a <xref:System.StackOverflowException>.</span></span>  
  
- <span data-ttu-id="b798b-114">En determinadas condiciones, las estructuras que pasan a un método se tratan como tipos de referencia en lugar de tipos de valor en las compilaciones de versión.</span><span class="sxs-lookup"><span data-stu-id="b798b-114">Under certain conditions, structures passed to a method are treated as reference types rather than value types in Release builds.</span></span> <span data-ttu-id="b798b-115">Una de las manifestaciones de este problema es que los elementos individuales de una colección aparecen en un orden inesperado.</span><span class="sxs-lookup"><span data-stu-id="b798b-115">One of the manifestations of this issue is that the individual items in a collection appear in an unexpected order.</span></span>  
  
- <span data-ttu-id="b798b-116">En determinadas condiciones, la comparación de los valores <xref:System.UInt16> con su conjunto de bits altos es incorrecta si se habilita la optimización.</span><span class="sxs-lookup"><span data-stu-id="b798b-116">Under certain conditions, the comparison of <xref:System.UInt16> values with their high bit set is incorrect if optimization is enabled.</span></span>  
  
- <span data-ttu-id="b798b-117">En determinadas condiciones, especialmente al indexar los valores de matriz, la inicialización de la memoria mediante la instrucción IL <xref:System.Reflection.Emit.OpCodes.Initblk?displayProperty=nameWithType> puede inicializar la memoria con un valor incorrecto.</span><span class="sxs-lookup"><span data-stu-id="b798b-117">Under certain conditions, particularly when initializing array values, memory initialization by the <xref:System.Reflection.Emit.OpCodes.Initblk?displayProperty=nameWithType> IL instruction may initialize memory with an incorrect value.</span></span> <span data-ttu-id="b798b-118">Esto puede producir una excepción no controlada o resultados incorrectos.</span><span class="sxs-lookup"><span data-stu-id="b798b-118">This can result either in an unhandled exception or incorrect output.</span></span>  
  
- <span data-ttu-id="b798b-119">En determinadas condiciones poco frecuentes, una prueba de bits condicional puede devolver el valor <xref:System.Boolean> incorrecto o producir una excepción si se habilitan las optimizaciones del compilador.</span><span class="sxs-lookup"><span data-stu-id="b798b-119">Under certain rare conditions, a conditional bit test can return the incorrect <xref:System.Boolean> value or throw an exception if compiler optimizations are enabled.</span></span>  
  
- <span data-ttu-id="b798b-120">En determinadas condiciones, si se utiliza una instrucción `if` para comprobar una condición antes de entrar en un bloque `try` y en la salida del bloque `try`, y se evalúa la misma condición en el bloque `catch` o `finally`, el compilador JIT de 64 bits nuevo quita la condición `if` del bloque `catch` o `finally` cuando optimiza el código.</span><span class="sxs-lookup"><span data-stu-id="b798b-120">Under certain conditions, if an `if` statement is used to test for a condition before entering  a `try` block and in the exit from the `try` block, and the same condition is evaluated in the `catch` or `finally` block, the new 64-bit JIT compiler removes the `if` condition from the `catch` or `finally` block when it optimizes code.</span></span> <span data-ttu-id="b798b-121">Como resultado, el código dentro de la instrucción `if` en el bloque `catch` o `finally` se ejecuta de forma incondicional.</span><span class="sxs-lookup"><span data-stu-id="b798b-121">As a result, code inside the `if` statement in the `catch` or `finally` block is executed unconditionally.</span></span>  
  
<a name="General"></a>

## <a name="mitigation-of-known-issues"></a><span data-ttu-id="b798b-122">Mitigación de problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="b798b-122">Mitigation of known issues</span></span>  

 <span data-ttu-id="b798b-123">Si encuentra los problemas mencionados anteriormente, puede solucionarlos realizando las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="b798b-123">If you encounter the issues listed above, you can address them by doing any of the following:</span></span>  
  
- <span data-ttu-id="b798b-124">Actualizar a the .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="b798b-124">Upgrade to the .NET Framework 4.6.2.</span></span> <span data-ttu-id="b798b-125">El nuevo compilador de 64 bits incluido con .NET Framework 4.6.2 soluciona estos problemas conocidos.</span><span class="sxs-lookup"><span data-stu-id="b798b-125">The new 64-bit compiler included with the .NET Framework 4.6.2 addresses each of these known issues.</span></span>  
  
- <span data-ttu-id="b798b-126">Asegurarse de que su versión Windows está actualizada ejecutando Windows Update.</span><span class="sxs-lookup"><span data-stu-id="b798b-126">Ensure that your version of Windows is up to date by running Windows Update.</span></span> <span data-ttu-id="b798b-127">Las actualizaciones de servicio de .NET Framework 4.6 y 4.6.1 solucionan los problemas excepto <xref:System.NullReferenceException> en una operación de conversión unboxing.</span><span class="sxs-lookup"><span data-stu-id="b798b-127">Service updates to the .NET Framework 4.6 and 4.6.1 address each of these issues except the <xref:System.NullReferenceException> in an unboxing operation.</span></span>  
  
- <span data-ttu-id="b798b-128">Compilación con el compilador JIT de 64 bits más antiguo.</span><span class="sxs-lookup"><span data-stu-id="b798b-128">Compile with the older 64-bit JIT compiler.</span></span> <span data-ttu-id="b798b-129">Vea la sección [Mitigación de otros problemas](#Other) sección para obtener más información sobre el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b798b-129">See the [Mitigation of other issues](#Other) section for more information on how to do this.</span></span>  
  
<a name="Other"></a>

## <a name="mitigation-of-other-issues"></a><span data-ttu-id="b798b-130">Mitigación de otros problemas</span><span class="sxs-lookup"><span data-stu-id="b798b-130">Mitigation of other issues</span></span>  

 <span data-ttu-id="b798b-131">Si detecta cualquier otra diferencia en el comportamiento entre el código compilado con el compilador de 64 bits antiguo y el compilador de 64 bits nuevo, o entre las versiones de depuración y publicación de la aplicación que se compilan con el nuevo compilador JIT de 64 bits, puede realizar el siguiente procedimiento para compilar la aplicación con el compilador JIT de 64 bits anterior:</span><span class="sxs-lookup"><span data-stu-id="b798b-131">If you encounter any other difference in behavior between code compiled with the older 64-bit compiler and the new 64-bit JIT compiler, or between the debug and release versions of your app that are both compiled with the new 64-bit JIT compiler, you can do the following to compile your app with the older 64-bit JIT compiler:</span></span>  
  
- <span data-ttu-id="b798b-132">Según la aplicación, se puede agregar el elemento [\<useLegacyJit>](../configure-apps/file-schema/runtime/uselegacyjit-element.md) al archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b798b-132">On a per-application basis, you can add the [\<useLegacyJit>](../configure-apps/file-schema/runtime/uselegacyjit-element.md) element to your application's configuration file.</span></span> <span data-ttu-id="b798b-133">Lo siguiente deshabilita la compilación con el nuevo compilador JIT de 64 bits y en su lugar usa el compilador JIT de 64 bits hereado.</span><span class="sxs-lookup"><span data-stu-id="b798b-133">The following disables compilation with the new 64-bit JIT compiler and instead uses the legacy 64-bit JIT compiler.</span></span>  
  
    ```xml  
    <?xml version ="1.0"?>  
    <configuration>  
        <runtime>  
           <useLegacyJit enabled="1" />  
        </runtime>  
    </configuration>  
    ```  
  
- <span data-ttu-id="b798b-134">Según el usuario, puede agregar un valor `REG_DWORD` con el nombre `useLegacyJit` a la clave `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` del registro.</span><span class="sxs-lookup"><span data-stu-id="b798b-134">On a per-user basis, you can add a `REG_DWORD` value named `useLegacyJit` to the `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key of the registry.</span></span> <span data-ttu-id="b798b-135">El valor 1 permite al compilador JIT de 64 bits hereado; un valor de 0 lo deshabilita y habilita el nuevo compilador JIT de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="b798b-135">A value of 1 enables the legacy 64-bit JIT compiler; a value of 0 disables it and enables the new 64-bit JIT compiler.</span></span>  
  
- <span data-ttu-id="b798b-136">Según el equipo, puede agregar un valor `REG_DWORD` con el nombre `useLegacyJit` a la clave `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` del registro.</span><span class="sxs-lookup"><span data-stu-id="b798b-136">On a per-machine basis, you can add a `REG_DWORD` value named `useLegacyJit` to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` key of the registry.</span></span> <span data-ttu-id="b798b-137">El valor 1 permite al compilador JIT de 64 bits hereado; un valor de 0 lo deshabilita y habilita el nuevo compilador JIT de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="b798b-137">A value of 1 enables the legacy 64-bit JIT compiler; a value of 0 disables it and enables the new 64-bit JIT compiler.</span></span>  
  
 <span data-ttu-id="b798b-138">También puede informar del problema indicándonos el error en [Microsoft Connect](https://connect.microsoft.com/VisualStudio).</span><span class="sxs-lookup"><span data-stu-id="b798b-138">You can also let us know about the problem by reporting a bug on [Microsoft Connect](https://connect.microsoft.com/VisualStudio).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b798b-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="b798b-139">See also</span></span>

- [<span data-ttu-id="b798b-140">Compatibilidad de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="b798b-140">Application compatibility</span></span>](application-compatibility.md)
- [<span data-ttu-id="b798b-141">Elemento \<useLegacyJit></span><span class="sxs-lookup"><span data-stu-id="b798b-141">\<useLegacyJit> Element</span></span>](../configure-apps/file-schema/runtime/uselegacyjit-element.md)
