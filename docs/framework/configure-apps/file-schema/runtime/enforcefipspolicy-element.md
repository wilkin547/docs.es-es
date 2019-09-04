---
title: <enforceFIPSPolicy> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f90abf9f6c2bc0aed2cf01558b2c0cca4e967e81
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252644"
---
# <a name="enforcefipspolicy-element"></a><span data-ttu-id="bdfb3-102">\<enforceFIPSPolicy >, elemento</span><span class="sxs-lookup"><span data-stu-id="bdfb3-102">\<enforceFIPSPolicy> Element</span></span>
<span data-ttu-id="bdfb3-103">Especifica si se debe exigir un requisito de configuración del equipo que indique que los algoritmos criptográficos deben cumplir con los Estándares federales de procesamiento de la información (FIPS).</span><span class="sxs-lookup"><span data-stu-id="bdfb3-103">Specifies whether to enforce a computer configuration requirement that cryptographic algorithms must comply with the Federal Information Processing Standards (FIPS).</span></span>  
  
<span data-ttu-id="bdfb3-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bdfb3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bdfb3-105">&nbsp;&nbsp;[ **\<> en tiempo de ejecución**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="bdfb3-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="bdfb3-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<enforceFIPSPolicy>**</span><span class="sxs-lookup"><span data-stu-id="bdfb3-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<enforceFIPSPolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdfb3-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bdfb3-107">Syntax</span></span>  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bdfb3-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bdfb3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="bdfb3-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bdfb3-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="bdfb3-110">Attributes</span></span>  
  
|<span data-ttu-id="bdfb3-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="bdfb3-111">Attribute</span></span>|<span data-ttu-id="bdfb3-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bdfb3-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bdfb3-113">enabled</span><span class="sxs-lookup"><span data-stu-id="bdfb3-113">enabled</span></span>|<span data-ttu-id="bdfb3-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="bdfb3-115">Especifica si se debe habilitar la aplicación de un requisito de configuración de equipo de que los algoritmos criptográficos deben ser compatibles con FIPS.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-115">Specifies whether to enable the enforcement of a computer configuration requirement that cryptographic algorithms must be compliant with FIPS.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="bdfb3-116">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="bdfb3-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="bdfb3-117">Valor</span><span class="sxs-lookup"><span data-stu-id="bdfb3-117">Value</span></span>|<span data-ttu-id="bdfb3-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bdfb3-118">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="bdfb3-119">Si el equipo está configurado para requerir que los algoritmos criptográficos sean conformes a FIPS, se aplicará ese requisito.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-119">If your computer is configured to require cryptographic algorithms to be FIPS compliant, that requirement is enforced.</span></span> <span data-ttu-id="bdfb3-120">Si una clase implementa un algoritmo que no es compatible con FIPS, los constructores o `Create` métodos de esa clase inician excepciones cuando se ejecutan en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-120">If a class implements an algorithm that is not compliant with FIPS, the constructors or `Create` methods for that class throw exceptions when they are run on that computer.</span></span> <span data-ttu-id="bdfb3-121">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="bdfb3-122">No es necesario que los algoritmos criptográficos que usa la aplicación sean compatibles con FIPS, independientemente de la configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-122">Cryptographic algorithms that are used by the application are not required to be compliant with FIPS, regardless of computer configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bdfb3-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bdfb3-123">Child Elements</span></span>  
 <span data-ttu-id="bdfb3-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bdfb3-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bdfb3-125">Parent Elements</span></span>  
  
|<span data-ttu-id="bdfb3-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="bdfb3-126">Element</span></span>|<span data-ttu-id="bdfb3-127">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bdfb3-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bdfb3-128">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="bdfb3-129">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bdfb3-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bdfb3-130">Remarks</span></span>  
 <span data-ttu-id="bdfb3-131">A partir del .NET Framework 2,0, la creación de clases que implementan algoritmos criptográficos se controla mediante la configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-131">Starting with the .NET Framework 2.0, the creation of classes that implement cryptographic algorithms is controlled by the configuration of the computer.</span></span> <span data-ttu-id="bdfb3-132">Si el equipo está configurado para requerir que los algoritmos sean compatibles con FIPS, y una clase implementa un algoritmo que no es compatible con FIPS, cualquier intento de crear una instancia de esa clase produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-132">If the computer is configured to require algorithms to be compliant with FIPS, and a class implements an algorithm that is not compliant with FIPS, any attempt to create an instance of that class throws an exception.</span></span> <span data-ttu-id="bdfb3-133">Los constructores producen <xref:System.InvalidOperationException> una excepción y `Create` los métodos producen <xref:System.Reflection.TargetInvocationException> una excepción con una <xref:System.InvalidOperationException> excepción interna.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-133">Constructors throw an <xref:System.InvalidOperationException> exception, and `Create` methods throw a <xref:System.Reflection.TargetInvocationException> exception with an inner <xref:System.InvalidOperationException> exception.</span></span>  
  
 <span data-ttu-id="bdfb3-134">Si la aplicación se ejecuta en equipos cuyas configuraciones requieren el cumplimiento de FIPS, y la aplicación usa un algoritmo que no es compatible con FIPS, puede usar este elemento en el archivo de configuración para evitar que el Common Language Runtime (CLR) de aplicando la compatibilidad con FIPS.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-134">If your application runs on computers whose configurations require compliance with FIPS, and your application uses an algorithm that is not compliant with FIPS, you can use this element in your configuration file to prevent the common language runtime (CLR) from enforcing FIPS compliance.</span></span> <span data-ttu-id="bdfb3-135">Este elemento se presentó en el .NET Framework 2,0 Service Pack 1.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-135">This element was introduced in the .NET Framework 2.0 Service Pack 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bdfb3-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bdfb3-136">Example</span></span>  
 <span data-ttu-id="bdfb3-137">En el ejemplo siguiente se muestra cómo evitar que CLR aplique la compatibilidad con FIPS.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-137">The following example shows how to prevent the CLR from enforcing FIPS compliance.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bdfb3-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="bdfb3-138">See also</span></span>

- [<span data-ttu-id="bdfb3-139">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="bdfb3-139">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="bdfb3-140">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="bdfb3-140">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="bdfb3-141">Modelo de criptografía</span><span class="sxs-lookup"><span data-stu-id="bdfb3-141">Cryptography Model</span></span>](../../../../standard/security/cryptography-model.md)
