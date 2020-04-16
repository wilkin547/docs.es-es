---
title: Tipos integrados para primitivas comunes en el lenguaje XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML language primitives [XAML Services]
- XAML [XAML Services], built-in types
- x:String [XAML Services]
- x:TimeSpan [XAML Services]
- x:Byte [XAML Services]
- x:Double [XAML Services]
- XAML [XAML Services], types
- x:Uri [XAML Services]
- XAML built-in types [XAML Services]
- x:Int64 [XAML Services]
- x:Single [XAML Services]
- x:Int32 [XAML Services]
ms.assetid: 11de2f08-5b95-4989-b5ec-5178eb968184
ms.openlocfilehash: 3bd486ee66c5f9a32621416638bb7575025f7dee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433059"
---
# <a name="built-in-types-for-common-xaml-language-primitives"></a><span data-ttu-id="ef78d-102">Tipos integrados para primitivas de lenguaje XAML comunes</span><span class="sxs-lookup"><span data-stu-id="ef78d-102">Built-in types for common XAML language primitives</span></span>

<span data-ttu-id="ef78d-103">XAML 2009 presenta la compatibilidad de nivel de lenguaje XAML con varios tipos de datos que son primitivas usadas con frecuencia en Common Language Runtime (CLR) y otros lenguajes de programación.</span><span class="sxs-lookup"><span data-stu-id="ef78d-103">XAML 2009 introduces XAML language-level support for several data types that are frequently used primitives in the common language runtime (CLR) and in other programming languages.</span></span> <span data-ttu-id="ef78d-104">XAML 2009 agrega compatibilidad con estas primitivas: `x:Object`, `x:Boolean`, `x:Char`, `x:String`, `x:Decimal`, `x:Single`, `x:Double`, `x:Int16`, `x:Int32`, `x:Int64`, `x:TimeSpan`, `x:Uri`, `x:Byte`y `x:Array`</span><span class="sxs-lookup"><span data-stu-id="ef78d-104">XAML 2009 adds support for these primitives: `x:Object`, `x:Boolean`, `x:Char`, `x:String`, `x:Decimal`, `x:Single`, `x:Double`, `x:Int16`, `x:Int32`, `x:Int64`, `x:TimeSpan`, `x:Uri`, `x:Byte`, and `x:Array`</span></span>

## <a name="previous-techniques-for-language-primitives-in-xaml-markup"></a><span data-ttu-id="ef78d-105">Técnicas anteriores para las primitivas del lenguaje en el marcado XAML</span><span class="sxs-lookup"><span data-stu-id="ef78d-105">Previous Techniques for Language Primitives in XAML Markup</span></span>

 <span data-ttu-id="ef78d-106">En XAML para versiones anteriores de WPF, se podía hacer referencia a las primitivas del lenguaje CLR si se asignaba el ensamblado y el espacio de nombres que contenían una clase de definición de primitiva CLR para .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ef78d-106">In XAML for previous WPF versions, you could reference the CLR language primitives by mapping the assembly and namespace that contained a CLR primitive definition class for the .NET Framework.</span></span> <span data-ttu-id="ef78d-107">La mayoría se encuentra en el ensamblado mscorlib y el espacio de nombres <xref:System> .</span><span class="sxs-lookup"><span data-stu-id="ef78d-107">Most of these are in the mscorlib assembly and <xref:System> namespace.</span></span> <span data-ttu-id="ef78d-108">Por ejemplo, para usar <xref:System.Int32>, podría declarar la siguiente asignación (con un uso de ejemplo mostrado a continuación):</span><span class="sxs-lookup"><span data-stu-id="ef78d-108">For example, to use <xref:System.Int32>, you could declare the following mapping (with an example usage shown thereafter):</span></span>

```xaml
<Application xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <Application.Resources>
    <sys:Int32 x:Key="intMeaning">42</sys:Int32>
  </Application.Resources>
</Application>
```

## <a name="xaml-2009-language-primitives"></a><span data-ttu-id="ef78d-109">Primitivas del lenguaje XAML 2009</span><span class="sxs-lookup"><span data-stu-id="ef78d-109">XAML 2009 Language Primitives</span></span>

<span data-ttu-id="ef78d-110">Por convención, se muestran las primitivas del lenguaje para XAML y todos los demás elementos del lenguaje XAML, incluido el prefijo `x:` .</span><span class="sxs-lookup"><span data-stu-id="ef78d-110">By convention, the language primitives for XAML and all other XAML language elements are shown, including the `x:` prefix.</span></span> <span data-ttu-id="ef78d-111">Así es como se usan normalmente los elementos del lenguaje XAML en el marcado del mundo real.</span><span class="sxs-lookup"><span data-stu-id="ef78d-111">This is how XAML language elements are typically used in real-world markup.</span></span> <span data-ttu-id="ef78d-112">Esta convención se sigue en la documentación conceptual de XAML en WPF y también en la especificación XAML.</span><span class="sxs-lookup"><span data-stu-id="ef78d-112">This convention is followed in the conceptual documentation for XAML in WPF and also in the XAML specification.</span></span>

### <a name="xobject"></a><span data-ttu-id="ef78d-113">x:Object</span><span class="sxs-lookup"><span data-stu-id="ef78d-113">x:Object</span></span>

<span data-ttu-id="ef78d-114">En copias de seguridad de CLR, la primitiva `x:Object` corresponde a <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="ef78d-114">For CLR backing, the `x:Object` primitive corresponds to <xref:System.Object>.</span></span>

<span data-ttu-id="ef78d-115">Esta primitiva no se usa normalmente en el marcado de aplicaciones, pero puede resultar útil en algunos escenarios como la comprobación de la capacidad de asignación en un sistema de tipos XAML.</span><span class="sxs-lookup"><span data-stu-id="ef78d-115">This primitive is not typically used in application markup, but might be useful for some scenarios such as checking assignability in a XAML type system.</span></span>

### <a name="xboolean"></a><span data-ttu-id="ef78d-116">x:Boolean</span><span class="sxs-lookup"><span data-stu-id="ef78d-116">x:Boolean</span></span>

<span data-ttu-id="ef78d-117">En copias de seguridad de CLR, la primitiva `x:Boolean` corresponde a <xref:System.Boolean>.</span><span class="sxs-lookup"><span data-stu-id="ef78d-117">For CLR backing, the `x:Boolean` primitive corresponds to <xref:System.Boolean>.</span></span>

<span data-ttu-id="ef78d-118">XAML analiza los valores de `x:Boolean` como si no distinguieran entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ef78d-118">XAML parses values for `x:Boolean` as case insensitive.</span></span> <span data-ttu-id="ef78d-119">Tenga en cuenta que `x:Bool` no es una alternativa aceptada.</span><span class="sxs-lookup"><span data-stu-id="ef78d-119">Note that `x:Bool` is not an accepted alternative.</span></span> <span data-ttu-id="ef78d-120">Para la definición de especificación del lenguaje XAML, vea [ \[MS-XAML\] Sections 5.2.17 y 5.4.11](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="ef78d-120">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.17 and 5.4.11](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xchar"></a><span data-ttu-id="ef78d-121">x:Char</span><span class="sxs-lookup"><span data-stu-id="ef78d-121">x:Char</span></span>

<span data-ttu-id="ef78d-122">En copias de seguridad de CLR, la primitiva `x:Char` corresponde a <xref:System.Char>.</span><span class="sxs-lookup"><span data-stu-id="ef78d-122">For CLR backing, the `x:Char` primitive corresponds to <xref:System.Char>.</span></span>

<span data-ttu-id="ef78d-123">Los tipos de cadena y carácter tienen interacción con la codificación general del archivo en el nivel XML.</span><span class="sxs-lookup"><span data-stu-id="ef78d-123">String and char types have interaction with the overall encoding of the file at the XML level.</span></span> <span data-ttu-id="ef78d-124">Para obtener la definición de especificación del lenguaje XAML, vea [ \[Las secciones 5.2.7 y 5.4.1 de MS-XAML.\] ](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="ef78d-124">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.7 and 5.4.1](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xstring"></a><span data-ttu-id="ef78d-125">x:String</span><span class="sxs-lookup"><span data-stu-id="ef78d-125">x:String</span></span>

<span data-ttu-id="ef78d-126">En copias de seguridad de CLR, la primitiva `x:String` corresponde a <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ef78d-126">For CLR backing, the `x:String` primitive corresponds to <xref:System.String>.</span></span>

<span data-ttu-id="ef78d-127">Los tipos de cadena y carácter tienen interacción con la codificación general del archivo en el nivel XML.</span><span class="sxs-lookup"><span data-stu-id="ef78d-127">String and char types have interaction with the overall encoding of the file at the XML level.</span></span> <span data-ttu-id="ef78d-128">Para obtener la definición de especificación del lenguaje XAML, vea [ \[Secciones\] 5.2.6 de MS-XAML](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="ef78d-128">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.6](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xdecimal"></a><span data-ttu-id="ef78d-129">x:Decimal</span><span class="sxs-lookup"><span data-stu-id="ef78d-129">x:Decimal</span></span>

<span data-ttu-id="ef78d-130">En copias de seguridad de CLR, la primitiva `x:Decimal` corresponde a <xref:System.Decimal>.</span><span class="sxs-lookup"><span data-stu-id="ef78d-130">For CLR backing, the `x:Decimal` primitive corresponds to <xref:System.Decimal>.</span></span>

<span data-ttu-id="ef78d-131">El análisis XAML se `en-US` realiza intrínsecamente en la referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="ef78d-131">XAML parsing is inherently done under `en-US` culture.</span></span> <span data-ttu-id="ef78d-132">En la referencia cultural `en-US` , el separador correcto de los componentes de un decimal es siempre un punto (`.`) independientemente de la configuración de referencia cultural del entorno de desarrollo o del destino de cliente final donde se carga XAML en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ef78d-132">Under `en-US` culture, the correct separator for the components of a decimal is always a period (`.`) regardless of culture settings of the development environment, or of the eventual client target where the XAML is loaded at run time.</span></span>

<span data-ttu-id="ef78d-133">Para la definición de especificación del lenguaje XAML, vea [ \[MS-XAML\] Sections 5.2.14 y 5.4.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="ef78d-133">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.14 and 5.4.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xsingle"></a><span data-ttu-id="ef78d-134">x:Single</span><span class="sxs-lookup"><span data-stu-id="ef78d-134">x:Single</span></span>

<span data-ttu-id="ef78d-135">En copias de seguridad de CLR, la primitiva `x:Single` corresponde a <xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="ef78d-135">For CLR backing, the `x:Single` primitive corresponds to <xref:System.Single>.</span></span>

<span data-ttu-id="ef78d-136">Además de los valores numéricos, la sintaxis de texto de `x:Single` también permite los tokens `Infinity`, `-Infinity`y `NaN`.</span><span class="sxs-lookup"><span data-stu-id="ef78d-136">In addition to the numeric values, text syntax for `x:Single` also permits the tokens `Infinity`, `-Infinity`, and `NaN`.</span></span> <span data-ttu-id="ef78d-137">En los tokens se distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ef78d-137">These tokens are treated as case sensitive.</span></span>

<span data-ttu-id="ef78d-138">`x:Single` puede admitir valores en formato de notación científica si el primer carácter de la sintaxis de texto es `e` o `E`.</span><span class="sxs-lookup"><span data-stu-id="ef78d-138">`x:Single` can support values in scientific notation form, if the first character in text syntax is `e` or `E`.</span></span>

<span data-ttu-id="ef78d-139">Para obtener la definición de especificación del lenguaje XAML, vea [ \[MS-XAML\] Sections 5.2.8 y 5.4.2](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="ef78d-139">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.8 and 5.4.2](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xdouble"></a><span data-ttu-id="ef78d-140">x:Double</span><span class="sxs-lookup"><span data-stu-id="ef78d-140">x:Double</span></span>

<span data-ttu-id="ef78d-141">En copias de seguridad de CLR, la primitiva `x:Double` corresponde a <xref:System.Double>.</span><span class="sxs-lookup"><span data-stu-id="ef78d-141">For CLR backing, the `x:Double` primitive corresponds to <xref:System.Double>.</span></span>

<span data-ttu-id="ef78d-142">Además de los valores numéricos, la sintaxis de texto de `x:Double` permite los tokens `Infinity`, `-Infinity`y `NaN`.</span><span class="sxs-lookup"><span data-stu-id="ef78d-142">In addition to the numeric values, text syntax for `x:Double` permits the tokens `Infinity`, `-Infinity`, and `NaN`.</span></span> <span data-ttu-id="ef78d-143">En los tokens se distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ef78d-143">These tokens are treated as case sensitive.</span></span>

<span data-ttu-id="ef78d-144">`x:Double` puede admitir valores en formato de notación científica.</span><span class="sxs-lookup"><span data-stu-id="ef78d-144">`x:Double` can support values in scientific notation form.</span></span> <span data-ttu-id="ef78d-145">Use el carácter `e` o `E` para presentar la parte del exponente.</span><span class="sxs-lookup"><span data-stu-id="ef78d-145">Use the character `e` or `E` to introduce the exponent portion.</span></span>

<span data-ttu-id="ef78d-146">Para la definición de especificación del lenguaje XAML, vea [ \[MS-XAML\] Sections 5.2.9 y 5.4.3](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="ef78d-146">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.9 and 5.4.3](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xint16"></a><span data-ttu-id="ef78d-147">x:Int16</span><span class="sxs-lookup"><span data-stu-id="ef78d-147">x:Int16</span></span>

<span data-ttu-id="ef78d-148">En copias de seguridad de CLR, la primitiva `x:Int16` corresponde a <xref:System.Int16> y `x:Int16` se trata como un valor con signo.</span><span class="sxs-lookup"><span data-stu-id="ef78d-148">For CLR backing, the `x:Int16` primitive corresponds to <xref:System.Int16> and `x:Int16` is treated as signed.</span></span> <span data-ttu-id="ef78d-149">En XAML, la ausencia de un signo más (`+`) en la sintaxis de texto se considera como un valor con signo positivo.</span><span class="sxs-lookup"><span data-stu-id="ef78d-149">In XAML, the absence of a plus (`+`) sign in text syntax is implied as a positive signed value.</span></span>

<span data-ttu-id="ef78d-150">Para la definición de especificación del lenguaje XAML, vea [ \[MS-XAML\] Sections 5.2.11 y 5.4.5](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="ef78d-150">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.11 and 5.4.5](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xint32"></a><span data-ttu-id="ef78d-151">x:Int32</span><span class="sxs-lookup"><span data-stu-id="ef78d-151">x:Int32</span></span>

<span data-ttu-id="ef78d-152">En copias de seguridad de CLR, la primitiva `x:Int32` corresponde a <xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="ef78d-152">For CLR backing, the `x:Int32` primitive corresponds to <xref:System.Int32>.</span></span> <span data-ttu-id="ef78d-153">`x:Int32` se trata como un valor con signo.</span><span class="sxs-lookup"><span data-stu-id="ef78d-153">`x:Int32` is treated as signed.</span></span> <span data-ttu-id="ef78d-154">En XAML, la ausencia de un signo más (`+`) en la sintaxis de texto se considera como un valor con signo positivo.</span><span class="sxs-lookup"><span data-stu-id="ef78d-154">In XAML, the absence of a plus (`+`) sign in text syntax is implied as a positive signed value.</span></span>

<span data-ttu-id="ef78d-155">Para la definición de especificación del lenguaje XAML, vea [ \[MS-XAML\] Sections 5.2.12 y 5.4.6](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="ef78d-155">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.12 and 5.4.6](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xint64"></a><span data-ttu-id="ef78d-156">x:Int64</span><span class="sxs-lookup"><span data-stu-id="ef78d-156">x:Int64</span></span>

<span data-ttu-id="ef78d-157">En copias de seguridad de CLR, la primitiva `x:Int64` corresponde a <xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="ef78d-157">For CLR backing, the `x:Int64` primitive corresponds to <xref:System.Int64>.</span></span> <span data-ttu-id="ef78d-158">`x:Int64` se trata como un valor con signo.</span><span class="sxs-lookup"><span data-stu-id="ef78d-158">`x:Int64` is treated as signed.</span></span> <span data-ttu-id="ef78d-159">En XAML, la ausencia de un signo más (`+`) en la sintaxis de texto se considera como un valor con signo positivo.</span><span class="sxs-lookup"><span data-stu-id="ef78d-159">In XAML, the absence of a plus (`+`) sign in text syntax is implied as a positive signed value.</span></span>

<span data-ttu-id="ef78d-160">Para la definición de especificación del lenguaje XAML, vea [ \[MS-XAML\] Sections 5.2.13 y 5.4.7](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="ef78d-160">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.13 and 5.4.7](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xtimespan"></a><span data-ttu-id="ef78d-161">x:TimeSpan</span><span class="sxs-lookup"><span data-stu-id="ef78d-161">x:TimeSpan</span></span>

<span data-ttu-id="ef78d-162">En copias de seguridad de CLR, la primitiva `x:TimeSpan` corresponde a <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="ef78d-162">For CLR backing, the `x:TimeSpan` primitive corresponds to <xref:System.TimeSpan>.</span></span>

<span data-ttu-id="ef78d-163">El análisis XAML para el formato de `en-US` fecha y hora se realiza intrínsecamente en la referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="ef78d-163">XAML parsing for time-date format is inherently done under `en-US` culture.</span></span>

<span data-ttu-id="ef78d-164">Para la definición de especificación del lenguaje XAML, vea [ \[MS-XAML\] Sections 5.2.16 y 5.4.10](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="ef78d-164">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.16 and 5.4.10](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xuri"></a><span data-ttu-id="ef78d-165">x:Uri</span><span class="sxs-lookup"><span data-stu-id="ef78d-165">x:Uri</span></span>

<span data-ttu-id="ef78d-166">En copias de seguridad de CLR, la primitiva `x:Uri` corresponde a <xref:System.Uri>.</span><span class="sxs-lookup"><span data-stu-id="ef78d-166">For CLR backing, the `x:Uri` primitive corresponds to <xref:System.Uri>.</span></span>

<span data-ttu-id="ef78d-167">La comprobación de los protocolos no forma parte de la definición de XAML para `x:Uri`.</span><span class="sxs-lookup"><span data-stu-id="ef78d-167">Checking for protocols is not part of the XAML definition for `x:Uri`.</span></span>

<span data-ttu-id="ef78d-168">Para la definición de especificación del lenguaje XAML, vea [ \[MS-XAML\] Sections 5.2.15 y 5.4.9](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="ef78d-168">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.15 and 5.4.9](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xbyte"></a><span data-ttu-id="ef78d-169">x:Byte</span><span class="sxs-lookup"><span data-stu-id="ef78d-169">x:Byte</span></span>

<span data-ttu-id="ef78d-170">En copias de seguridad de CLR, la primitiva `x:Byte` corresponde a <xref:System.Byte>.</span><span class="sxs-lookup"><span data-stu-id="ef78d-170">For CLR backing, the `x:Byte` primitive corresponds to <xref:System.Byte>.</span></span> <span data-ttu-id="ef78d-171"><xref:System.Byte>  /  A `x:Byte` se trata como sin firmar.</span><span class="sxs-lookup"><span data-stu-id="ef78d-171">A <xref:System.Byte> / `x:Byte` is treated as unsigned.</span></span>

<span data-ttu-id="ef78d-172">Para obtener la definición de especificación del lenguaje XAML, vea [ \[MS-XAML\] Sections 5.2.10 y 5.4.4](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="ef78d-172">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.10 and 5.4.4](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

### <a name="xarray"></a><span data-ttu-id="ef78d-173">x:Array</span><span class="sxs-lookup"><span data-stu-id="ef78d-173">x:Array</span></span>

<span data-ttu-id="ef78d-174">En copias de seguridad de CLR, la primitiva `x:Array` corresponde a <xref:System.Array>.</span><span class="sxs-lookup"><span data-stu-id="ef78d-174">For CLR backing, the `x:Array` primitive corresponds to <xref:System.Array>.</span></span>

<span data-ttu-id="ef78d-175">Puede definir una matriz en XAML 2006 con una sintaxis de extensión de marcado; sin embargo, la sintaxis de XAML 2009 es una primitiva definida por el lenguaje que no necesita acceso a una extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="ef78d-175">You can define an array in XAML 2006  by using a markup extension syntax; however, the XAML 2009 syntax is a language-defined primitive that does not require accessing a markup extension.</span></span> <span data-ttu-id="ef78d-176">Para más información sobre la compatibilidad con XAML 2006, vea [x:Array Markup Extension](xarray-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="ef78d-176">For more information about XAML 2006 support, see [x:Array Markup Extension](xarray-markup-extension.md).</span></span>

<span data-ttu-id="ef78d-177">Para obtener la definición de especificación del lenguaje XAML, vea [ \[Secciones\] 5.2.18 de MS-XAML](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="ef78d-177">For the XAML language specification definition, see [\[MS-XAML\] Sections 5.2.18](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

## <a name="wpf-support"></a><span data-ttu-id="ef78d-178">Compatibilidad de WPF</span><span class="sxs-lookup"><span data-stu-id="ef78d-178">WPF Support</span></span>

<span data-ttu-id="ef78d-179">En WPF, puede usar las características de XAML 2009 pero solo para XAML que no se haya compilado por marcado.</span><span class="sxs-lookup"><span data-stu-id="ef78d-179">In WPF, you can use XAML 2009 features but only for XAML that is not markup-compiled.</span></span> <span data-ttu-id="ef78d-180">XAML compilado por marcado para WPF y el formulario BAML de XAML no admiten de momento las palabras clave y características de XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="ef78d-180">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>

<span data-ttu-id="ef78d-181">Un escenario donde puede usar las características de XAML 2009 junto con WPF es si crea XAML dinámico y, a continuación, carga ese XAML en un gráfico de objetos y tiempo de ejecución de WPF con <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ef78d-181">A scenario where you can use XAML 2009 features together with WPF is if you author loose XAML and you then load that XAML into a WPF runtime and object graph with <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ef78d-182"><xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> de WPF y su <xref:System.Windows.Markup.XamlReader.Load%2A> pueden procesar las características y palabras clave del lenguaje XAML 2009 en una representación de gráfico de objetos válido.</span><span class="sxs-lookup"><span data-stu-id="ef78d-182">The WPF <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> and its <xref:System.Windows.Markup.XamlReader.Load%2A> can process XAML 2009 language keywords and features into a valid object graph representation.</span></span>
