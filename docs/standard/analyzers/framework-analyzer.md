---
title: 'Analizadores de .NET Framework: .NET'
description: Obtenga información sobre cómo usar los analizadores de .NET Framework en el paquete de analizadores de .NET Framework para buscar y tratar los riesgos de seguridad
author: billwagner
ms.author: wiwagn
ms.date: 01/25/2018
ms.technology: dotnet-standard
ms.openlocfilehash: dd69671e709549fe0ad0f582e4d09b43f7321df2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "78156002"
---
# <a name="the-net-framework-analyzer"></a><span data-ttu-id="fd70a-103">Analizador de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fd70a-103">The .NET Framework Analyzer</span></span>

<span data-ttu-id="fd70a-104">Puede usar el analizador de .NET Framework para buscar posibles problemas en el código de aplicación basado en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fd70a-104">You can use the .NET Framework Analyzer to find potential issues in your .NET Framework-based application code.</span></span> <span data-ttu-id="fd70a-105">Este analizador busca posibles problemas y sugiere correcciones.</span><span class="sxs-lookup"><span data-stu-id="fd70a-105">This analyzer finds potential issues and suggests fixes to them.</span></span>

<span data-ttu-id="fd70a-106">El analizador se ejecuta de forma interactiva en Visual Studio mientras escribe el código o como parte de una compilación de integración continua.</span><span class="sxs-lookup"><span data-stu-id="fd70a-106">The analyzer runs interactively in Visual Studio as you write your code or as part of a CI build.</span></span> <span data-ttu-id="fd70a-107">Debe agregar el analizador al proyecto lo antes posible en el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="fd70a-107">You should add the analyzer to your project as early as possible in your development.</span></span> <span data-ttu-id="fd70a-108">Cuanto antes encuentre los posibles problemas del código, más fácil será corregirlos.</span><span class="sxs-lookup"><span data-stu-id="fd70a-108">The sooner you find any potential issues in your code, the easier they are to fix.</span></span> <span data-ttu-id="fd70a-109">Aun así, puede agregarlo en cualquier momento del ciclo de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="fd70a-109">However, you can add it at any time in the development cycle.</span></span> <span data-ttu-id="fd70a-110">Busca cualquier problema con el código existente y advierte sobre nuevos problemas mientras desarrolla.</span><span class="sxs-lookup"><span data-stu-id="fd70a-110">It finds any issues with the existing code and warns about new issues as you keep developing.</span></span>

## <a name="installing-and-configuring-the-net-framework-analyzer"></a><span data-ttu-id="fd70a-111">Instalar y configurar el analizador de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fd70a-111">Installing and configuring the .NET Framework Analyzer</span></span>

<span data-ttu-id="fd70a-112">Los analizadores de .NET Framework deben instalarse como un paquete NuGet en todos los proyectos en los que quiera ejecutarlos.</span><span class="sxs-lookup"><span data-stu-id="fd70a-112">The .NET Framework Analyzers must be installed as a NuGet package on every project where you want them to run.</span></span> <span data-ttu-id="fd70a-113">Solo los tiene que agregar un desarrollador al proyecto.</span><span class="sxs-lookup"><span data-stu-id="fd70a-113">Only one developer needs to add them to the project.</span></span> <span data-ttu-id="fd70a-114">El paquete de analizadores es una dependencia del proyecto y se ejecutará en el equipo de todos los desarrolladores cuando tengan la solución actualizada.</span><span class="sxs-lookup"><span data-stu-id="fd70a-114">The analyzer package is a project dependency and will run on every developer's machine once it has the updated solution.</span></span>

<span data-ttu-id="fd70a-115">El analizador de .NET Framework se entrega en el paquete NuGet [Microsoft.NetFramework.Analyzers](https://www.nuget.org/packages/Microsoft.NetFramework.Analyzers/).</span><span class="sxs-lookup"><span data-stu-id="fd70a-115">The .NET Framework Analyzer is delivered in the [Microsoft.NetFramework.Analyzers](https://www.nuget.org/packages/Microsoft.NetFramework.Analyzers/) NuGet package.</span></span> <span data-ttu-id="fd70a-116">Este paquete solo proporciona los analizadores específicos de .NET Framework, que incluye los analizadores de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fd70a-116">This package provides only the analyzers specific to the .NET Framework, which includes security analyzers.</span></span> <span data-ttu-id="fd70a-117">En la mayoría de los casos, le interesará el paquete NuGet [Microsoft.CodeAnalysis.FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers).</span><span class="sxs-lookup"><span data-stu-id="fd70a-117">In most cases, you'll want the [Microsoft.CodeAnalysis.FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers) NuGet package.</span></span>
<span data-ttu-id="fd70a-118">El paquete de agregados FxCopAnalyzers contiene todos los analizadores de .NET Framework incluidos en el paquete Framework.Analyzers, así como los siguientes analizadores:</span><span class="sxs-lookup"><span data-stu-id="fd70a-118">The FxCopAnalyzers aggregate package contains all the framework analyzers included in the Framework.Analyzers package as well as the following analyzers:</span></span>

- <span data-ttu-id="fd70a-119">[Microsoft.CodeQuality.Analyzers](https://www.nuget.org/packages/Microsoft.CodeQuality.Analyzers): proporciona instrucciones generales e instrucciones para las API de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="fd70a-119">[Microsoft.CodeQuality.Analyzers](https://www.nuget.org/packages/Microsoft.CodeQuality.Analyzers): Provides general guidance and guidance for .NET Standard APIs</span></span>
- <span data-ttu-id="fd70a-120">[Microsoft.NetCore.Analyzers](https://www.nuget.org/packages/Microsoft.NetCore.Analyzers): proporciona analizadores específicos para las API de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fd70a-120">[Microsoft.NetCore.Analyzers](https://www.nuget.org/packages/Microsoft.NetCore.Analyzers): Provides analyzers specific to .NET Core APIs.</span></span>
- <span data-ttu-id="fd70a-121">[Text.Analyzers](https://www.nuget.org/packages/Text.Analyzers): proporciona instrucciones para el texto incluido como código, incluidos los comentarios.</span><span class="sxs-lookup"><span data-stu-id="fd70a-121">[Text.Analyzers](https://www.nuget.org/packages/Text.Analyzers): Provides guidance for text included as code, including comments.</span></span>

<span data-ttu-id="fd70a-122">Para instalarlo, haga clic con el botón derecho en el proyecto y seleccione "Administrar dependencias".</span><span class="sxs-lookup"><span data-stu-id="fd70a-122">To install it, right-click on the project, and select "Manage Dependencies".</span></span>
<span data-ttu-id="fd70a-123">En el explorador de NuGet, busque "NetFramework Analyzer" o, si lo prefiere, "Fx Cop Analyzer".</span><span class="sxs-lookup"><span data-stu-id="fd70a-123">From the NuGet explorer, search for "NetFramework Analyzer", or if you prefer, "Fx Cop Analyzer".</span></span> <span data-ttu-id="fd70a-124">Instale la versión estable más reciente en todos los proyectos de la solución.</span><span class="sxs-lookup"><span data-stu-id="fd70a-124">Install the latest stable version in all projects in your solution.</span></span>

## <a name="using-the-net-framework-analyzer"></a><span data-ttu-id="fd70a-125">Usar el analizador de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fd70a-125">Using the .NET Framework Analyzer</span></span>

<span data-ttu-id="fd70a-126">Una vez instalado el paquete NuGet, compile la solución.</span><span class="sxs-lookup"><span data-stu-id="fd70a-126">Once the NuGet package is installed, build your solution.</span></span> <span data-ttu-id="fd70a-127">El analizador notificará los problemas que encuentre en el código base.</span><span class="sxs-lookup"><span data-stu-id="fd70a-127">The analyzer will report any issues it locates in your codebase.</span></span> <span data-ttu-id="fd70a-128">Los problemas se notifican como advertencias en la ventana Lista de errores de Visual Studio, como se muestra en la siguiente imagen:</span><span class="sxs-lookup"><span data-stu-id="fd70a-128">The issues are reported as warnings in the Visual Studio Error List window, as shown in the following image:</span></span>

![problemas notificados por el analizador de marco](./media/framework-analyzers-2.png)

<span data-ttu-id="fd70a-130">Al escribir el código, verá subrayados ondulados debajo de cualquier posible problema del código.</span><span class="sxs-lookup"><span data-stu-id="fd70a-130">As you write code, you see squiggles underneath any potential issue in your code.</span></span>
<span data-ttu-id="fd70a-131">Mantenga el mouse sobre cualquier problema y verá detalles sobre este, además de sugerencias de cualquier posible corrección, como se muestra en la siguiente imagen:</span><span class="sxs-lookup"><span data-stu-id="fd70a-131">Hover over any issue and you see details about the issue, and suggestions for any possible fix, as shown in the following image:</span></span>

![informe interactivo de los problemas encontrados por el analizador de .NET Framework](./media/framework-analyzers-1.png)

<span data-ttu-id="fd70a-133">Los analizadores examinan el código en la solución y proporcionan una lista de advertencias de cualquiera de estos problemas:</span><span class="sxs-lookup"><span data-stu-id="fd70a-133">The analyzers examine the code in your solution and provide you with a list of warnings for any of these issues:</span></span>

### <a name="ca1058-types-should-not-extend-certain-base-types"></a><span data-ttu-id="fd70a-134">CA1058: Los tipos no deben ampliar ciertos tipos base</span><span class="sxs-lookup"><span data-stu-id="fd70a-134">CA1058: Types should not extend certain base types</span></span>

<span data-ttu-id="fd70a-135">Hay un pequeño número de tipos en .NET Framework de los que no debe derivar directamente.</span><span class="sxs-lookup"><span data-stu-id="fd70a-135">There are a small number of types in the .NET Framework that you should not derived from directly.</span></span>

<span data-ttu-id="fd70a-136">**Categoría:** diseño</span><span class="sxs-lookup"><span data-stu-id="fd70a-136">**Category:** Design</span></span>

<span data-ttu-id="fd70a-137">**Gravedad:** advertencia</span><span class="sxs-lookup"><span data-stu-id="fd70a-137">**Severity:** Warning</span></span>

<span data-ttu-id="fd70a-138">Información adicional: [CA1058: Los tipos no deben ampliar ciertos tipos base](/visualstudio/code-quality/ca1058-types-should-not-extend-certain-base-types)</span><span class="sxs-lookup"><span data-stu-id="fd70a-138">Additional information: [CA:1058: Types should not extend certain base types](/visualstudio/code-quality/ca1058-types-should-not-extend-certain-base-types)</span></span>

### <a name="ca2153-do-not-catch-corrupted-state-exceptions"></a><span data-ttu-id="fd70a-139">CA2153: No capturar excepciones de estado dañado</span><span class="sxs-lookup"><span data-stu-id="fd70a-139">CA2153: Do not catch corrupted state exceptions</span></span>

<span data-ttu-id="fd70a-140">Si se capturan excepciones de estado dañado, podrían enmascarar errores (por ejemplo, infracciones de acceso), lo que da como resultado un estado incoherente de la ejecución o lo que facilita a los atacantes poner en peligro un sistema.</span><span class="sxs-lookup"><span data-stu-id="fd70a-140">Catching corrupted state exceptions could mask errors (such as access violations), resulting in an inconsistent state of execution or making it easier for attackers to compromise a system.</span></span> <span data-ttu-id="fd70a-141">En su lugar, detecte y controle un conjunto más específico de tipos de excepción o vuelva a producir la excepción.</span><span class="sxs-lookup"><span data-stu-id="fd70a-141">Instead, catch and handle a more specific set of exception type(s) or re-throw the exception</span></span>

<span data-ttu-id="fd70a-142">**Categoría:** seguridad</span><span class="sxs-lookup"><span data-stu-id="fd70a-142">**Category:** Security</span></span>

<span data-ttu-id="fd70a-143">**Gravedad:** advertencia</span><span class="sxs-lookup"><span data-stu-id="fd70a-143">**Severity:** Warning</span></span>

<span data-ttu-id="fd70a-144">Información adicional: [CA2153: No capturar excepciones de estado dañado](/visualstudio/code-quality/ca2153-avoid-handling-corrupted-state-exceptions)</span><span class="sxs-lookup"><span data-stu-id="fd70a-144">Additional information: [## CA2153: Do not catch corrupted state exceptions](/visualstudio/code-quality/ca2153-avoid-handling-corrupted-state-exceptions)</span></span>

### <a name="ca2229-implement-serialization-constructors"></a><span data-ttu-id="fd70a-145">CA2229: Implementar constructores de serialización</span><span class="sxs-lookup"><span data-stu-id="fd70a-145">CA2229: Implement serialization constructors</span></span>

<span data-ttu-id="fd70a-146">El analizador genera esta advertencia cuando crea un tipo que implementa la interfaz <xref:System.Runtime.Serialization.ISerializable> pero no define el constructor de serialización necesario.</span><span class="sxs-lookup"><span data-stu-id="fd70a-146">The analyzer generates this warning when you create a type that implements the <xref:System.Runtime.Serialization.ISerializable> interface but does not define the required serialization constructor.</span></span> <span data-ttu-id="fd70a-147">Para corregir una infracción de esta regla, implemente el constructor de serialización.</span><span class="sxs-lookup"><span data-stu-id="fd70a-147">To fix a violation of this rule, implement the serialization constructor.</span></span> <span data-ttu-id="fd70a-148">Para una clase sellada, marque el constructor como privado; de lo contrario, márquelo como protegido.</span><span class="sxs-lookup"><span data-stu-id="fd70a-148">For a sealed class, make the constructor private; otherwise, make it protected.</span></span> <span data-ttu-id="fd70a-149">El constructor de serialización tiene la siguiente signatura:</span><span class="sxs-lookup"><span data-stu-id="fd70a-149">The serialization constructor has the following signature:</span></span>

```csharp
public class MyItemType
{
    // The special constructor is used to deserialize values.
    public MyItemType(SerializationInfo info, StreamingContext context)
    {
        // implementation removed.
    }
}
```

<span data-ttu-id="fd70a-150">**Categoría:** uso</span><span class="sxs-lookup"><span data-stu-id="fd70a-150">**Category:** Usage</span></span>

<span data-ttu-id="fd70a-151">**Gravedad:** advertencia</span><span class="sxs-lookup"><span data-stu-id="fd70a-151">**Severity:** Warning</span></span>

<span data-ttu-id="fd70a-152">Información adicional: [CA2229: Implementar constructores de serialización](/visualstudio/code-quality/ca2229-implement-serialization-constructors)</span><span class="sxs-lookup"><span data-stu-id="fd70a-152">Additional information: [CA2229: Implement serialization constructors](/visualstudio/code-quality/ca2229-implement-serialization-constructors)</span></span>

### <a name="ca2235-mark-all-non-serializable-fields"></a><span data-ttu-id="fd70a-153">CA2235: Marcar todos los campos no serializables</span><span class="sxs-lookup"><span data-stu-id="fd70a-153">CA2235: Mark all non-serializable fields</span></span>

<span data-ttu-id="fd70a-154">Un campo de instancia de un tipo que no es serializable se declara en un tipo que es serializable.</span><span class="sxs-lookup"><span data-stu-id="fd70a-154">An instance field of a type that is not serializable is declared in a type that is serializable.</span></span> <span data-ttu-id="fd70a-155">Debe marcar explícitamente ese campo con el <xref:System.NonSerializedAttribute> para corregir esta advertencia.</span><span class="sxs-lookup"><span data-stu-id="fd70a-155">You must explicitly mark that field with the <xref:System.NonSerializedAttribute> to fix this warning.</span></span>

<span data-ttu-id="fd70a-156">**Categoría:** uso</span><span class="sxs-lookup"><span data-stu-id="fd70a-156">**Category:** Usage</span></span>

<span data-ttu-id="fd70a-157">**Gravedad:** advertencia</span><span class="sxs-lookup"><span data-stu-id="fd70a-157">**Severity:** Warning</span></span>

<span data-ttu-id="fd70a-158">Información adicional: [CA2235: Marcar todos los campos no serializables](/visualstudio/code-quality/ca2235-mark-all-non-serializable-fields)</span><span class="sxs-lookup"><span data-stu-id="fd70a-158">Additional information: [CA2235: Mark all non-serializable fields](/visualstudio/code-quality/ca2235-mark-all-non-serializable-fields)</span></span>

### <a name="ca2237-mark-iserializable-types-with-serializable"></a><span data-ttu-id="fd70a-159">CA2237: Marcar los tipos ISerializable con serializable</span><span class="sxs-lookup"><span data-stu-id="fd70a-159">CA2237: Mark ISerializable types with serializable</span></span>

<span data-ttu-id="fd70a-160">Para que Common Language Runtime reconozca los tipos como serializables, deben marcarse con el atributo <xref:System.SerializableAttribute> incluso si el tipo usa una rutina de serialización personalizada al implementar la interfaz <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="fd70a-160">To be recognized by the common language runtime as serializable, types must be marked by using the <xref:System.SerializableAttribute> attribute even when the type uses a custom serialization routine by implementing the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span>

<span data-ttu-id="fd70a-161">**Categoría:** uso</span><span class="sxs-lookup"><span data-stu-id="fd70a-161">**Category:** Usage</span></span>

<span data-ttu-id="fd70a-162">**Gravedad:** advertencia</span><span class="sxs-lookup"><span data-stu-id="fd70a-162">**Severity:** Warning</span></span>

<span data-ttu-id="fd70a-163">Información adicional: [CA2237: Marcar los tipos ISerializable con serializable](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)</span><span class="sxs-lookup"><span data-stu-id="fd70a-163">Additional information: [CA2237: Mark ISerializable types with serializable](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)</span></span>

### <a name="ca3075-insecure-dtd-processing-in-xml"></a><span data-ttu-id="fd70a-164">CA3075: Procesamiento de DTD no seguro en XML</span><span class="sxs-lookup"><span data-stu-id="fd70a-164">CA3075: Insecure DTD processing in XML</span></span>

<span data-ttu-id="fd70a-165">Si usa instancias de <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> no seguras o hace referencia a orígenes de entidades externas, el analizador podría aceptar entradas que no sean de confianza y revelar información confidencial a atacantes.</span><span class="sxs-lookup"><span data-stu-id="fd70a-165">If you use insecure <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> instances or reference external entity sources, the parser may accept untrusted input and disclose sensitive information to attackers.</span></span>  

<span data-ttu-id="fd70a-166">**Categoría:** seguridad</span><span class="sxs-lookup"><span data-stu-id="fd70a-166">**Category:** Security</span></span>

<span data-ttu-id="fd70a-167">**Gravedad:** advertencia</span><span class="sxs-lookup"><span data-stu-id="fd70a-167">**Severity:** Warning</span></span>

<span data-ttu-id="fd70a-168">Información adicional: [A3075: Procesamiento de DTD no seguro en XML](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)</span><span class="sxs-lookup"><span data-stu-id="fd70a-168">Additional information: [A3075: Insecure DTD processing in XML](/visualstudio/code-quality/ca2237-mark-iserializable-types-with-serializableattribute)</span></span>

### <a name="ca5350-do-not-use-weak-cryptographic-algorithms"></a><span data-ttu-id="fd70a-169">CA5350: No usar algoritmos criptográficos no seguros</span><span class="sxs-lookup"><span data-stu-id="fd70a-169">CA5350: Do not use weak cryptographic algorithms</span></span>

<span data-ttu-id="fd70a-170">Los algoritmos criptográficos se degradan con el paso del tiempo, ya que los ataques aumentan.</span><span class="sxs-lookup"><span data-stu-id="fd70a-170">Cryptographic algorithms degrade over time as attacks become more advanced.</span></span> <span data-ttu-id="fd70a-171">En función del tipo y la aplicación de este algoritmo criptográfico, una mayor degradación de su intensidad de cifrado puede permitir a los atacantes leer mensajes cifrados, manipular mensajes cifrados, falsificar firmas digitales, manipular contenido con hash o poner en peligro los sistemas de cifrado basados en este algoritmo.</span><span class="sxs-lookup"><span data-stu-id="fd70a-171">Depending on the type and application of this cryptographic algorithm, further degradation of its cryptographic strength may allow attackers to read enciphered messages, tamper with enciphered messages, forge digital signatures, tamper with hashed content, or otherwise compromise any cryptosystem based on this algorithm.</span></span> <span data-ttu-id="fd70a-172">Para el cifrado, use un algoritmo AES (AES-256, AES-192 y AES-128 son aceptables) con una longitud de clave mayor o igual que 128 bits.</span><span class="sxs-lookup"><span data-stu-id="fd70a-172">For encryption, use an AES algorithm (AES-256, AES-192 and AES-128 are acceptable) with a key length greater than or equal to 128 bits.</span></span> <span data-ttu-id="fd70a-173">Para el hash, use una función hash de la familia SHA-2, como SHA-2 512, SHA-2 384 o SHA-2 256.</span><span class="sxs-lookup"><span data-stu-id="fd70a-173">For hashing, use a hashing function in the SHA-2 family, such as SHA-2 512, SHA-2 384, or SHA-2 256.</span></span>

<span data-ttu-id="fd70a-174">**Categoría:** seguridad</span><span class="sxs-lookup"><span data-stu-id="fd70a-174">**Category:** Security</span></span>

<span data-ttu-id="fd70a-175">**Gravedad:** advertencia</span><span class="sxs-lookup"><span data-stu-id="fd70a-175">**Severity:** Warning</span></span>

<span data-ttu-id="fd70a-176">Información adicional: [CA5350: No usar algoritmos criptográficos no seguros](/visualstudio/code-quality/ca5350-do-not-use-weak-cryptographic-algorithms)</span><span class="sxs-lookup"><span data-stu-id="fd70a-176">Additional information: [CA5350: Do not use weak cryptographic algorithms](/visualstudio/code-quality/ca5350-do-not-use-weak-cryptographic-algorithms)</span></span>

### <a name="ca5351-do-not-use-broken-cryptographic-algorithms"></a><span data-ttu-id="fd70a-177">CA5351: No usar algoritmos criptográficos rotos</span><span class="sxs-lookup"><span data-stu-id="fd70a-177">CA5351: Do not use broken cryptographic algorithms</span></span>

<span data-ttu-id="fd70a-178">Existe un ataque que, a nivel computacional, puede interrumpir este algoritmo.</span><span class="sxs-lookup"><span data-stu-id="fd70a-178">An attack making it computationally feasible to break this algorithm exists.</span></span> <span data-ttu-id="fd70a-179">De esta forma, los atacantes pueden interrumpir las garantías cifradas que debe proporcionar por diseño.</span><span class="sxs-lookup"><span data-stu-id="fd70a-179">This allows attackers to break the cryptographic guarantees it is designed to provide.</span></span> <span data-ttu-id="fd70a-180">En función del tipo y la aplicación de este algoritmo criptográfico, puede permitir a los atacantes leer mensajes cifrados, manipular mensajes cifrados, falsificar firmas digitales, manipular contenido con hash o poner en peligro los sistemas de cifrado basados en este algoritmo.</span><span class="sxs-lookup"><span data-stu-id="fd70a-180">Depending on the type and application of this cryptographic algorithm, this may allow attackers to read enciphered messages, tamper with enciphered messages, forge digital signatures, tamper with hashed content, or otherwise compromise any cryptosystem based on this algorithm.</span></span> <span data-ttu-id="fd70a-181">Para el cifrado, use un algoritmo AES (AES-256, AES-192 y AES-128 son aceptables) con una longitud de clave mayor o igual que 128 bits.</span><span class="sxs-lookup"><span data-stu-id="fd70a-181">For encryption, use an AES algorithm (AES-256, AES-192 and AES-128 are acceptable) with a key length greater than or equal to 128 bits.</span></span> <span data-ttu-id="fd70a-182">Para el hash, use una función hash de la familia SHA-2, como SHA512, SHA384 o SHA256.</span><span class="sxs-lookup"><span data-stu-id="fd70a-182">For hashing, use a hashing function in the SHA-2 family, such as SHA512, SHA384, or SHA256.</span></span> <span data-ttu-id="fd70a-183">Para las firmas digitales, use RSA con una longitud de clave mayor o igual que 2048 bits, o ECDSA con una longitud de clave mayor o igual que 256 bits.</span><span class="sxs-lookup"><span data-stu-id="fd70a-183">For digital signatures, use RSA with a key length greater than or equal to 2048-bits, or ECDSA with a key length greater than or equal to 256 bits.</span></span>

<span data-ttu-id="fd70a-184">**Categoría:** seguridad</span><span class="sxs-lookup"><span data-stu-id="fd70a-184">**Category:** Security</span></span>

<span data-ttu-id="fd70a-185">**Gravedad:** advertencia</span><span class="sxs-lookup"><span data-stu-id="fd70a-185">**Severity:** Warning</span></span>

<span data-ttu-id="fd70a-186">Información adicional: [CA5351: No usar algoritmos criptográficos rotos](/visualstudio/code-quality/ca5351)</span><span class="sxs-lookup"><span data-stu-id="fd70a-186">Additional Information: [CA5351: Do not use broken cryptographic algorithms](/visualstudio/code-quality/ca5351)</span></span>
