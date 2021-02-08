---
description: 'Más información acerca de: <enforceFIPSPolicy> elemento'
title: <enforceFIPSPolicy> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
ms.openlocfilehash: d445570db634867a15b6d97d4e20186bd0641c2d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787076"
---
# <a name="enforcefipspolicy-element"></a><span data-ttu-id="a338b-103">\<enforceFIPSPolicy> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="a338b-103">\<enforceFIPSPolicy> Element</span></span>

<span data-ttu-id="a338b-104">Especifica si se debe exigir un requisito de configuración del equipo que indique que los algoritmos criptográficos deben cumplir con los Estándares federales de procesamiento de la información (FIPS).</span><span class="sxs-lookup"><span data-stu-id="a338b-104">Specifies whether to enforce a computer configuration requirement that cryptographic algorithms must comply with the Federal Information Processing Standards (FIPS).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<enforceFIPSPolicy>**  
  
## <a name="syntax"></a><span data-ttu-id="a338b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a338b-105">Syntax</span></span>  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a338b-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a338b-106">Attributes and Elements</span></span>  

 <span data-ttu-id="a338b-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a338b-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a338b-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="a338b-108">Attributes</span></span>  
  
|<span data-ttu-id="a338b-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="a338b-109">Attribute</span></span>|<span data-ttu-id="a338b-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="a338b-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a338b-111">enabled</span><span class="sxs-lookup"><span data-stu-id="a338b-111">enabled</span></span>|<span data-ttu-id="a338b-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="a338b-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="a338b-113">Especifica si se debe habilitar la aplicación de un requisito de configuración de equipo de que los algoritmos criptográficos deben ser compatibles con FIPS.</span><span class="sxs-lookup"><span data-stu-id="a338b-113">Specifies whether to enable the enforcement of a computer configuration requirement that cryptographic algorithms must be compliant with FIPS.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a338b-114">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="a338b-114">enabled Attribute</span></span>  
  
|<span data-ttu-id="a338b-115">Value</span><span class="sxs-lookup"><span data-stu-id="a338b-115">Value</span></span>|<span data-ttu-id="a338b-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="a338b-116">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="a338b-117">Si el equipo está configurado para requerir que los algoritmos criptográficos sean conformes a FIPS, se aplicará ese requisito.</span><span class="sxs-lookup"><span data-stu-id="a338b-117">If your computer is configured to require cryptographic algorithms to be FIPS compliant, that requirement is enforced.</span></span> <span data-ttu-id="a338b-118">Si una clase implementa un algoritmo que no es compatible con FIPS, los constructores o `Create` métodos de esa clase inician excepciones cuando se ejecutan en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="a338b-118">If a class implements an algorithm that is not compliant with FIPS, the constructors or `Create` methods for that class throw exceptions when they are run on that computer.</span></span> <span data-ttu-id="a338b-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a338b-119">This is the default.</span></span>|  
|`false`|<span data-ttu-id="a338b-120">No es necesario que los algoritmos criptográficos que usa la aplicación sean compatibles con FIPS, independientemente de la configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="a338b-120">Cryptographic algorithms that are used by the application are not required to be compliant with FIPS, regardless of computer configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a338b-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a338b-121">Child Elements</span></span>  

 <span data-ttu-id="a338b-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a338b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a338b-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a338b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a338b-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="a338b-124">Element</span></span>|<span data-ttu-id="a338b-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="a338b-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a338b-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a338b-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a338b-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a338b-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a338b-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a338b-128">Remarks</span></span>  

 <span data-ttu-id="a338b-129">A partir del .NET Framework 2,0, la creación de clases que implementan algoritmos criptográficos se controla mediante la configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="a338b-129">Starting with the .NET Framework 2.0, the creation of classes that implement cryptographic algorithms is controlled by the configuration of the computer.</span></span> <span data-ttu-id="a338b-130">Si el equipo está configurado para requerir que los algoritmos sean compatibles con FIPS, y una clase implementa un algoritmo que no es compatible con FIPS, cualquier intento de crear una instancia de esa clase produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="a338b-130">If the computer is configured to require algorithms to be compliant with FIPS, and a class implements an algorithm that is not compliant with FIPS, any attempt to create an instance of that class throws an exception.</span></span> <span data-ttu-id="a338b-131">Los constructores producen una <xref:System.InvalidOperationException> excepción y `Create` los métodos producen una <xref:System.Reflection.TargetInvocationException> excepción con una <xref:System.InvalidOperationException> excepción interna.</span><span class="sxs-lookup"><span data-stu-id="a338b-131">Constructors throw an <xref:System.InvalidOperationException> exception, and `Create` methods throw a <xref:System.Reflection.TargetInvocationException> exception with an inner <xref:System.InvalidOperationException> exception.</span></span>  
  
 <span data-ttu-id="a338b-132">Si la aplicación se ejecuta en equipos cuyas configuraciones requieren el cumplimiento de FIPS, y la aplicación usa un algoritmo que no es compatible con FIPS, puede usar este elemento en el archivo de configuración para evitar que el Common Language Runtime (CLR) Aplique la compatibilidad con FIPS.</span><span class="sxs-lookup"><span data-stu-id="a338b-132">If your application runs on computers whose configurations require compliance with FIPS, and your application uses an algorithm that is not compliant with FIPS, you can use this element in your configuration file to prevent the common language runtime (CLR) from enforcing FIPS compliance.</span></span> <span data-ttu-id="a338b-133">Este elemento se presentó en el .NET Framework 2,0 Service Pack 1.</span><span class="sxs-lookup"><span data-stu-id="a338b-133">This element was introduced in the .NET Framework 2.0 Service Pack 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a338b-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a338b-134">Example</span></span>  

 <span data-ttu-id="a338b-135">En el ejemplo siguiente se muestra cómo evitar que CLR aplique la compatibilidad con FIPS.</span><span class="sxs-lookup"><span data-stu-id="a338b-135">The following example shows how to prevent the CLR from enforcing FIPS compliance.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a338b-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="a338b-136">See also</span></span>

- [<span data-ttu-id="a338b-137">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="a338b-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a338b-138">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="a338b-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a338b-139">Modelo de criptografía</span><span class="sxs-lookup"><span data-stu-id="a338b-139">Cryptography Model</span></span>](../../../../standard/security/cryptography-model.md)
