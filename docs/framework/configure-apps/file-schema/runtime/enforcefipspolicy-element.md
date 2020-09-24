---
title: <enforceFIPSPolicy> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
ms.openlocfilehash: 864a371d4ad10585e672452ad85cc09d4b684068
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158843"
---
# <a name="enforcefipspolicy-element"></a><span data-ttu-id="b213c-102">\<enforceFIPSPolicy> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="b213c-102">\<enforceFIPSPolicy> Element</span></span>

<span data-ttu-id="b213c-103">Especifica si se debe exigir un requisito de configuración del equipo que indique que los algoritmos criptográficos deben cumplir con los Estándares federales de procesamiento de la información (FIPS).</span><span class="sxs-lookup"><span data-stu-id="b213c-103">Specifies whether to enforce a computer configuration requirement that cryptographic algorithms must comply with the Federal Information Processing Standards (FIPS).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<enforceFIPSPolicy>**  
  
## <a name="syntax"></a><span data-ttu-id="b213c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b213c-104">Syntax</span></span>  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b213c-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b213c-105">Attributes and Elements</span></span>  

 <span data-ttu-id="b213c-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b213c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b213c-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="b213c-107">Attributes</span></span>  
  
|<span data-ttu-id="b213c-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="b213c-108">Attribute</span></span>|<span data-ttu-id="b213c-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="b213c-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b213c-110">enabled</span><span class="sxs-lookup"><span data-stu-id="b213c-110">enabled</span></span>|<span data-ttu-id="b213c-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="b213c-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="b213c-112">Especifica si se debe habilitar la aplicación de un requisito de configuración de equipo de que los algoritmos criptográficos deben ser compatibles con FIPS.</span><span class="sxs-lookup"><span data-stu-id="b213c-112">Specifies whether to enable the enforcement of a computer configuration requirement that cryptographic algorithms must be compliant with FIPS.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b213c-113">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="b213c-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="b213c-114">Value</span><span class="sxs-lookup"><span data-stu-id="b213c-114">Value</span></span>|<span data-ttu-id="b213c-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="b213c-115">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="b213c-116">Si el equipo está configurado para requerir que los algoritmos criptográficos sean conformes a FIPS, se aplicará ese requisito.</span><span class="sxs-lookup"><span data-stu-id="b213c-116">If your computer is configured to require cryptographic algorithms to be FIPS compliant, that requirement is enforced.</span></span> <span data-ttu-id="b213c-117">Si una clase implementa un algoritmo que no es compatible con FIPS, los constructores o `Create` métodos de esa clase inician excepciones cuando se ejecutan en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="b213c-117">If a class implements an algorithm that is not compliant with FIPS, the constructors or `Create` methods for that class throw exceptions when they are run on that computer.</span></span> <span data-ttu-id="b213c-118">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b213c-118">This is the default.</span></span>|  
|`false`|<span data-ttu-id="b213c-119">No es necesario que los algoritmos criptográficos que usa la aplicación sean compatibles con FIPS, independientemente de la configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="b213c-119">Cryptographic algorithms that are used by the application are not required to be compliant with FIPS, regardless of computer configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b213c-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b213c-120">Child Elements</span></span>  

 <span data-ttu-id="b213c-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b213c-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b213c-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b213c-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b213c-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="b213c-123">Element</span></span>|<span data-ttu-id="b213c-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="b213c-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b213c-125">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b213c-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b213c-126">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b213c-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b213c-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b213c-127">Remarks</span></span>  

 <span data-ttu-id="b213c-128">A partir del .NET Framework 2,0, la creación de clases que implementan algoritmos criptográficos se controla mediante la configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="b213c-128">Starting with the .NET Framework 2.0, the creation of classes that implement cryptographic algorithms is controlled by the configuration of the computer.</span></span> <span data-ttu-id="b213c-129">Si el equipo está configurado para requerir que los algoritmos sean compatibles con FIPS, y una clase implementa un algoritmo que no es compatible con FIPS, cualquier intento de crear una instancia de esa clase produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="b213c-129">If the computer is configured to require algorithms to be compliant with FIPS, and a class implements an algorithm that is not compliant with FIPS, any attempt to create an instance of that class throws an exception.</span></span> <span data-ttu-id="b213c-130">Los constructores producen una <xref:System.InvalidOperationException> excepción y `Create` los métodos producen una <xref:System.Reflection.TargetInvocationException> excepción con una <xref:System.InvalidOperationException> excepción interna.</span><span class="sxs-lookup"><span data-stu-id="b213c-130">Constructors throw an <xref:System.InvalidOperationException> exception, and `Create` methods throw a <xref:System.Reflection.TargetInvocationException> exception with an inner <xref:System.InvalidOperationException> exception.</span></span>  
  
 <span data-ttu-id="b213c-131">Si la aplicación se ejecuta en equipos cuyas configuraciones requieren el cumplimiento de FIPS, y la aplicación usa un algoritmo que no es compatible con FIPS, puede usar este elemento en el archivo de configuración para evitar que el Common Language Runtime (CLR) Aplique la compatibilidad con FIPS.</span><span class="sxs-lookup"><span data-stu-id="b213c-131">If your application runs on computers whose configurations require compliance with FIPS, and your application uses an algorithm that is not compliant with FIPS, you can use this element in your configuration file to prevent the common language runtime (CLR) from enforcing FIPS compliance.</span></span> <span data-ttu-id="b213c-132">Este elemento se presentó en el .NET Framework 2,0 Service Pack 1.</span><span class="sxs-lookup"><span data-stu-id="b213c-132">This element was introduced in the .NET Framework 2.0 Service Pack 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b213c-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b213c-133">Example</span></span>  

 <span data-ttu-id="b213c-134">En el ejemplo siguiente se muestra cómo evitar que CLR aplique la compatibilidad con FIPS.</span><span class="sxs-lookup"><span data-stu-id="b213c-134">The following example shows how to prevent the CLR from enforcing FIPS compliance.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b213c-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b213c-135">See also</span></span>

- [<span data-ttu-id="b213c-136">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="b213c-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b213c-137">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="b213c-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="b213c-138">Modelo de criptografía</span><span class="sxs-lookup"><span data-stu-id="b213c-138">Cryptography Model</span></span>](../../../../standard/security/cryptography-model.md)
