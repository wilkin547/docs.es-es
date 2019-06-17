---
title: Lo obsoleto en la biblioteca de clases de .NET Framework
ms.custom: updateeachrelease
ms.date: 04/02/2019
helpviewer_keywords:
- obsolete [.NET Framework]
- what's obsolete [.NET Framework]
- deprecated [.NET Framework]
ms.assetid: d356a43a-73df-4ae2-a457-b9628074c7cd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 810f49581d4cb28987ea41237645f75c50388084
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690479"
---
# <a name="whats-obsolete-in-the-net-framework-class-library"></a><span data-ttu-id="9d412-102">Lo obsoleto en la biblioteca de clases de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9d412-102">What's obsolete in the .NET Framework class library</span></span>

<span data-ttu-id="9d412-103">.NET Framework cambia con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="9d412-103">The .NET Framework changes over time.</span></span> <span data-ttu-id="9d412-104">Cada nueva versión agrega nuevos tipos y miembros de tipos que proporcionan una nueva funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="9d412-104">Each new version adds new types and type members that provide new functionality.</span></span> <span data-ttu-id="9d412-105">Los tipos existentes y sus miembros también cambian con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="9d412-105">Existing types and their members also change over time.</span></span> <span data-ttu-id="9d412-106">Por ejemplo, algunos tipos pierden importancia cuando la tecnología que admiten es reemplazada por una nueva y algunos métodos son sustituidos por métodos más nuevos que resultan más cómodos o están más completos.</span><span class="sxs-lookup"><span data-stu-id="9d412-106">For example, some types become less important as the technology they support is replaced by a new technology, and some methods are superseded by newer methods that are either more convenient or more full-featured.</span></span>

<span data-ttu-id="9d412-107">.NET Framework y Common Language Runtime se esfuerzan por ser compatibles con versiones anteriores (permitir que aplicaciones que se desarrollaron con una versión de .NET Framework puedan ejecutarse en la versión siguiente de .NET Framework).</span><span class="sxs-lookup"><span data-stu-id="9d412-107">The .NET Framework and the common language runtime strive to support backward compatibility (allowing applications that were developed with one version of the .NET Framework to run on the next version of the .NET Framework).</span></span> <span data-ttu-id="9d412-108">Esto hace más difícil quitar simplemente un tipo o un miembro de tipo.</span><span class="sxs-lookup"><span data-stu-id="9d412-108">This makes it difficult to simply remove a type or a type member.</span></span> <span data-ttu-id="9d412-109">En su lugar, .NET Framework indica que no se debería seguir utilizando un tipo o un miembro de tipo marcándolo como obsoleto o desusado.</span><span class="sxs-lookup"><span data-stu-id="9d412-109">Instead, the .NET Framework indicates that a type or a type member should no longer be used by marking it as obsolete or deprecated.</span></span> <span data-ttu-id="9d412-110">El desuso de un tipo o un miembro implica marcarlo para que los desarrolladores sean conscientes de que va a desaparecer y tengan tiempo para reaccionar antes de su eliminación.</span><span class="sxs-lookup"><span data-stu-id="9d412-110">Deprecating a type or a member involves marking it so that developers are aware it will go away and have time to respond to its removal.</span></span> <span data-ttu-id="9d412-111">Sin embargo, el código existente que utiliza el tipo o el miembro continúa ejecutándose en la nueva versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9d412-111">However, existing code that uses the type or member continues to run in the new version of the .NET Framework.</span></span>

> [!NOTE]
> <span data-ttu-id="9d412-112">Los términos *obsoleto* y *en desuso* tienen el mismo significado cuando se aplican a los tipos y miembros de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9d412-112">The terms *obsolete* and *deprecated* have the same meaning when applied to the types and members of the .NET Framework.</span></span>

## <a name="the-obsoleteattribute-attribute"></a><span data-ttu-id="9d412-113">El atributo ObsoleteAttribute</span><span class="sxs-lookup"><span data-stu-id="9d412-113">The ObsoleteAttribute attribute</span></span>

<span data-ttu-id="9d412-114">.NET Framework indica que un tipo o un miembro de tipo está obsoleto marcándolo con el atributo <xref:System.ObsoleteAttribute>.</span><span class="sxs-lookup"><span data-stu-id="9d412-114">The .NET Framework indicates that a type or type member is obsolete by marking it with the <xref:System.ObsoleteAttribute> attribute.</span></span> <span data-ttu-id="9d412-115">La aplicación del atributo a un tipo o miembro indica que ese tipo o miembro se quitará de alguna versión futura de .NET Framework sin interrumpir el código compilado que utiliza este miembro.</span><span class="sxs-lookup"><span data-stu-id="9d412-115">Applying the attribute to a type or member indicates that type or member will be removed in some future version of the .NET Framework without breaking compiled code that uses that member.</span></span>

<span data-ttu-id="9d412-116">Además de indicar que un tipo o miembro de tipo está obsoleto, <xref:System.ObsoleteAttribute> define cómo administra el compilador el código fuente que incluye este tipo o miembro.</span><span class="sxs-lookup"><span data-stu-id="9d412-116">In addition to indicating that a type or a type member is obsolete, <xref:System.ObsoleteAttribute> defines how the compiler handles source code that includes that type or member.</span></span> <span data-ttu-id="9d412-117">El compilador puede compilar el código pero emitir un mensaje de advertencia o puede tratar el uso del tipo o miembro como un error.</span><span class="sxs-lookup"><span data-stu-id="9d412-117">The compiler can compile the code but emit a warning message, or it can treat the use of the type or member as an error.</span></span> <span data-ttu-id="9d412-118">En el primer caso, el código puede compilarse correctamente, pero un mensaje de advertencia indica que el tipo o miembro está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="9d412-118">In the first case, the code can successfully compile, but a warning message indicates that the type or member is obsolete.</span></span> <span data-ttu-id="9d412-119">En el segundo caso, se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="9d412-119">In the second case, compilation fails.</span></span>

<span data-ttu-id="9d412-120">Incluso si la compilación genera un error en lugar de un mensaje de advertencia, <xref:System.ObsoleteAttribute> no afecta al comportamiento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9d412-120">Even if compilation produces an error instead of a warning message, <xref:System.ObsoleteAttribute> does not affect run-time behavior.</span></span> <span data-ttu-id="9d412-121">Es decir, las aplicaciones que utilizan el tipo o miembro y que se han compilado correctamente siempre se ejecutarán correctamente.</span><span class="sxs-lookup"><span data-stu-id="9d412-121">That is, applications that use the type or member and that have compiled successfully will always run successfully.</span></span> <span data-ttu-id="9d412-122">Solo se produce un error en el intento de volver a compilar una aplicación que utiliza el tipo o miembro.</span><span class="sxs-lookup"><span data-stu-id="9d412-122">Only the attempt to recompile an application that uses the type or member fails.</span></span>

## <a name="how-to-handle-obsolete-types-and-members"></a><span data-ttu-id="9d412-123">Cómo controlar los tipos y miembros obsoletos</span><span class="sxs-lookup"><span data-stu-id="9d412-123">How to handle obsolete types and members</span></span>

<span data-ttu-id="9d412-124">Al actualizar y volver a compilar el código existente, el uso de un tipo o miembro obsoleto que genera una advertencia del compilador en su aplicación es absolutamente aceptable.</span><span class="sxs-lookup"><span data-stu-id="9d412-124">When you upgrade and recompile existing code, using an obsolete type or member that produces a compiler warning in your application is perfectly acceptable.</span></span> <span data-ttu-id="9d412-125">Sin embargo, debería revisar el mensaje de advertencia del compilador para determinar si tiene que cambiar el código de aplicación.</span><span class="sxs-lookup"><span data-stu-id="9d412-125">However, you should review the compiler warning message to determine whether you should change your application code.</span></span> <span data-ttu-id="9d412-126">Si el mensaje no indica ninguna alternativa adecuada, debe realizar una de las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="9d412-126">If the message does not point to a suitable alternative, you should do either of the following:</span></span>

- <span data-ttu-id="9d412-127">Cambie su código quitando el uso del tipo o miembro, si es posible.</span><span class="sxs-lookup"><span data-stu-id="9d412-127">Change your code by removing the use of the type or member, if possible.</span></span>

     <span data-ttu-id="9d412-128">o bien</span><span class="sxs-lookup"><span data-stu-id="9d412-128">-or-</span></span>

- <span data-ttu-id="9d412-129">Revise la documentación para que esta área de tecnología determine cómo responder al desuso.</span><span class="sxs-lookup"><span data-stu-id="9d412-129">Review the documentation for this technology area to determine how to respond to the deprecation.</span></span>

<span data-ttu-id="9d412-130">Puede decidir no volver a compilar un código existente con una versión posterior de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9d412-130">You may choose not to recompile existing code against a later version of the .NET Framework.</span></span> <span data-ttu-id="9d412-131">En su lugar, puede especificar la versión de .NET Framework con la que se ejecuta el código compilado existente.</span><span class="sxs-lookup"><span data-stu-id="9d412-131">Instead, you can specify the version of the .NET Framework against which your existing compiled code runs.</span></span> <span data-ttu-id="9d412-132">Por ejemplo, supongamos que tiene una aplicación llamada app1.exe compilada con .NET Framework 3.5, pero quiere que la aplicación se ejecute con .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="9d412-132">For example, suppose that you have an application named app1.exe that was compiled against the .NET Framework 3.5, but you want the application to run against the .NET Framework 4.5.</span></span> <span data-ttu-id="9d412-133">Para ello, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="9d412-133">This requires the following steps:</span></span>

1. <span data-ttu-id="9d412-134">Cree un archivo de configuración para el ejecutable principal y denomínelo *appName*.exe.config, donde *appName* es el nombre del ejecutable de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9d412-134">Create a configuration file for your main executable and name it *appName*.exe.config, where *appName* is the name of the application executable.</span></span> <span data-ttu-id="9d412-135">Para la aplicación denominada app1.exe en nuestro ejemplo, va a crear un archivo de configuración denominado app1.exe.config.</span><span class="sxs-lookup"><span data-stu-id="9d412-135">For the application named app1.exe in our example, you would create a configuration file named app1.exe.config.</span></span>

2. <span data-ttu-id="9d412-136">Agregue lo siguiente al archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="9d412-136">Add the following to the configuration file.</span></span>

    ```xml
    <configuration>
       <startup> 
          <supportedRuntime version="v4.0" />
       </startup>
    </configuration>
    ```

<span data-ttu-id="9d412-137">En la siguiente tabla se muestra una lista de los valores de cadena que puede asignar al atributo `version` para destinarlo a una versión concreta de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9d412-137">The following table lists the string values that you can assign to the `version` attribute to target a specific version of the .NET Framework:</span></span>

|<span data-ttu-id="9d412-138">Versión de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9d412-138">.NET Framework version</span></span>|<span data-ttu-id="9d412-139">Cadena de `version`</span><span class="sxs-lookup"><span data-stu-id="9d412-139">`version` string</span></span>|
|-|-|
|<span data-ttu-id="9d412-140">4.8</span><span class="sxs-lookup"><span data-stu-id="9d412-140">4.8</span></span>|<span data-ttu-id="9d412-141">v4.0</span><span class="sxs-lookup"><span data-stu-id="9d412-141">v4.0</span></span>|
|<span data-ttu-id="9d412-142">4.7 (incluidas 4.7.1 y 4.7.2)</span><span class="sxs-lookup"><span data-stu-id="9d412-142">4.7 (including 4.7.1 and 4.7.2)</span></span>|<span data-ttu-id="9d412-143">v4.0</span><span class="sxs-lookup"><span data-stu-id="9d412-143">v4.0</span></span>|
|<span data-ttu-id="9d412-144">4.6 (incluidas 4.6.1 y 4.6.2)</span><span class="sxs-lookup"><span data-stu-id="9d412-144">4.6 (including 4.6.1 and 4.6.2)</span></span>|<span data-ttu-id="9d412-145">v4.0</span><span class="sxs-lookup"><span data-stu-id="9d412-145">v4.0</span></span>|
|<span data-ttu-id="9d412-146">4.5 (incluidas 4.5.1 y 4.5.2)</span><span class="sxs-lookup"><span data-stu-id="9d412-146">4.5 (including 4.5.1 and 4.5.2)</span></span>|<span data-ttu-id="9d412-147">v4.0</span><span class="sxs-lookup"><span data-stu-id="9d412-147">v4.0</span></span>|
|<span data-ttu-id="9d412-148">4</span><span class="sxs-lookup"><span data-stu-id="9d412-148">4</span></span>|<span data-ttu-id="9d412-149">v4.0</span><span class="sxs-lookup"><span data-stu-id="9d412-149">v4.0</span></span>|
|<span data-ttu-id="9d412-150">3.5</span><span class="sxs-lookup"><span data-stu-id="9d412-150">3.5</span></span>|<span data-ttu-id="9d412-151">v2.0.50727</span><span class="sxs-lookup"><span data-stu-id="9d412-151">v2.0.50727</span></span>|
|<span data-ttu-id="9d412-152">2.0</span><span class="sxs-lookup"><span data-stu-id="9d412-152">2.0</span></span>|<span data-ttu-id="9d412-153">v2.0.50727</span><span class="sxs-lookup"><span data-stu-id="9d412-153">v2.0.50727</span></span>|
|<span data-ttu-id="9d412-154">1.1</span><span class="sxs-lookup"><span data-stu-id="9d412-154">1.1</span></span>|<span data-ttu-id="9d412-155">v1.1.4322</span><span class="sxs-lookup"><span data-stu-id="9d412-155">v1.1.4322</span></span>|
|<span data-ttu-id="9d412-156">1.0</span><span class="sxs-lookup"><span data-stu-id="9d412-156">1.0</span></span>|<span data-ttu-id="9d412-157">v1.0.3705</span><span class="sxs-lookup"><span data-stu-id="9d412-157">v1.0.3705</span></span>|

## <a name="obsolete-lists-for-the-net-framework-45-and-later-versions"></a><span data-ttu-id="9d412-158">Listas de elementos obsoletos en .NET Framework 4.5 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="9d412-158">Obsolete lists for the .NET Framework 4.5 and later versions</span></span>

- [<span data-ttu-id="9d412-159">Tipos obsoletos</span><span class="sxs-lookup"><span data-stu-id="9d412-159">Obsolete Types</span></span>](obsolete-types.md)
- [<span data-ttu-id="9d412-160">Miembros obsoletos</span><span class="sxs-lookup"><span data-stu-id="9d412-160">Obsolete Members</span></span>](obsolete-members.md)

## <a name="obsolete-lists-for-previous-versions"></a><span data-ttu-id="9d412-161">Listas de elementos obsoletos en versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="9d412-161">Obsolete lists for previous versions</span></span>

- <span data-ttu-id="9d412-162">[Tipos obsoletos en .NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee461503(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9d412-162">[Obsolete Types in the .NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee461503(v=vs.100))</span></span>

- <span data-ttu-id="9d412-163">[Miembros obsoletos en .NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee471421(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9d412-163">[Obsolete Members in the .NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee471421(v=vs.100))</span></span>

- <span data-ttu-id="9d412-164">[Lista de API obsoletas en .NET Framework 3.5](https://docs.microsoft.com/previous-versions/cc835481(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="9d412-164">[.NET Framework 3.5 Obsolete List](https://docs.microsoft.com/previous-versions/cc835481(v=msdn.10))</span></span>

- <span data-ttu-id="9d412-165">[Lista de API obsoletas en .NET Framework 2.0](https://docs.microsoft.com/previous-versions/aa497286(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="9d412-165">[.NET Framework 2.0 Obsolete List](https://docs.microsoft.com/previous-versions/aa497286(v=msdn.10))</span></span>

## <a name="see-also"></a><span data-ttu-id="9d412-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d412-166">See also</span></span>

- [<span data-ttu-id="9d412-167">\<supportedRuntime > Elemento</span><span class="sxs-lookup"><span data-stu-id="9d412-167">\<supportedRuntime> Element</span></span>](../configure-apps/file-schema/startup/supportedruntime-element.md)
