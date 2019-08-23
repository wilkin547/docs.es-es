---
title: <PreferComInsteadOfManagedRemoting> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c79c76717acf7ff309375313b30534dd0aff9399
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920704"
---
# <a name="prefercominsteadofmanagedremoting-element"></a><span data-ttu-id="29674-102">\<PreferComInsteadOfManagedRemoting >, elemento</span><span class="sxs-lookup"><span data-stu-id="29674-102">\<PreferComInsteadOfManagedRemoting> Element</span></span>
<span data-ttu-id="29674-103">Especifica si el tiempo de ejecución usará la interoperabilidad COM en lugar de la comunicación remota para todas las llamadas en los límites del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="29674-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
 <span data-ttu-id="29674-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="29674-104">\<configuration></span></span>  
<span data-ttu-id="29674-105">\<> en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="29674-105">\<runtime></span></span>  
<span data-ttu-id="29674-106">\<PreferComInsteadOfManagedRemoting></span><span class="sxs-lookup"><span data-stu-id="29674-106">\<PreferComInsteadOfManagedRemoting></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29674-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="29674-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29674-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="29674-108">Attributes and Elements</span></span>  
 <span data-ttu-id="29674-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="29674-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29674-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="29674-110">Attributes</span></span>  
  
|<span data-ttu-id="29674-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="29674-111">Attribute</span></span>|<span data-ttu-id="29674-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="29674-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="29674-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="29674-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="29674-114">Indica si el tiempo de ejecución utilizará la interoperabilidad COM en lugar de la comunicación remota entre los límites del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="29674-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="29674-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="29674-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="29674-116">Valor</span><span class="sxs-lookup"><span data-stu-id="29674-116">Value</span></span>|<span data-ttu-id="29674-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="29674-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="29674-118">El Runtime usará la comunicación remota en los límites del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="29674-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="29674-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="29674-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="29674-120">El Runtime usará la interoperabilidad COM en los límites del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="29674-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="29674-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="29674-121">Child Elements</span></span>  
 <span data-ttu-id="29674-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="29674-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="29674-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="29674-123">Parent Elements</span></span>  
  
|<span data-ttu-id="29674-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="29674-124">Element</span></span>|<span data-ttu-id="29674-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="29674-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="29674-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="29674-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="29674-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="29674-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29674-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="29674-128">Remarks</span></span>  
 <span data-ttu-id="29674-129">Al establecer el `enabled` atributo en `true`, el tiempo de ejecución se comporta de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="29674-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
- <span data-ttu-id="29674-130">El runtime no llama a [IUnknown:: QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) para una interfaz [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) cuando una interfaz [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) entra en el dominio a través de una interfaz com.</span><span class="sxs-lookup"><span data-stu-id="29674-130">The runtime does not call [IUnknown::QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="29674-131">En su lugar, crea un contenedor RCW ( [Runtime Callable wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) ) alrededor del objeto.</span><span class="sxs-lookup"><span data-stu-id="29674-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
- <span data-ttu-id="29674-132">El tiempo de ejecución devuelve E_NOINTERFACE cuando recibe `QueryInterface` una llamada a una interfaz [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) para cualquier contenedor CCW ( [com Callable wrapper](../../../../standard/native-interop/com-callable-wrapper.md) ) que se ha creado en este dominio.</span><span class="sxs-lookup"><span data-stu-id="29674-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../standard/native-interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="29674-133">Estos dos comportamientos garantizan que todas las llamadas a través de interfaces COM entre los objetos administrados a través de los límites del dominio de aplicación utilizan la interoperabilidad com y COM en lugar de la comunicación remota.</span><span class="sxs-lookup"><span data-stu-id="29674-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29674-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="29674-134">Example</span></span>  
 <span data-ttu-id="29674-135">En el ejemplo siguiente se muestra cómo especificar que el Runtime debe utilizar la interoperabilidad COM en los límites de aislamiento:</span><span class="sxs-lookup"><span data-stu-id="29674-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="29674-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="29674-136">See also</span></span>

- [<span data-ttu-id="29674-137">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="29674-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="29674-138">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="29674-138">Configuration File Schema</span></span>](../index.md)
