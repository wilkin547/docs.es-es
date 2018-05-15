---
title: '&lt;PreferComInsteadOfManagedRemoting&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4cac4ebb46fabad49e2e4e6a7d566522ca027094
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltprefercominsteadofmanagedremotinggt-element"></a><span data-ttu-id="b01c9-102">&lt;PreferComInsteadOfManagedRemoting&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="b01c9-102">&lt;PreferComInsteadOfManagedRemoting&gt; Element</span></span>
<span data-ttu-id="b01c9-103">Especifica si el tiempo de ejecución utilizará la interoperabilidad COM en lugar de comunicación remota para todas las llamadas a través de los límites del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b01c9-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
 <span data-ttu-id="b01c9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b01c9-104">\<configuration></span></span>  
<span data-ttu-id="b01c9-105">\<en tiempo de ejecución ></span><span class="sxs-lookup"><span data-stu-id="b01c9-105">\<runtime></span></span>  
<span data-ttu-id="b01c9-106">\<PreferComInsteadOfManagedRemoting ></span><span class="sxs-lookup"><span data-stu-id="b01c9-106">\<PreferComInsteadOfManagedRemoting></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b01c9-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b01c9-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b01c9-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b01c9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b01c9-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b01c9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b01c9-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="b01c9-110">Attributes</span></span>  
  
|<span data-ttu-id="b01c9-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="b01c9-111">Attribute</span></span>|<span data-ttu-id="b01c9-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b01c9-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="b01c9-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="b01c9-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="b01c9-114">Indica si el tiempo de ejecución utilizará la interoperabilidad COM en lugar de comunicación remota entre límites de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b01c9-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b01c9-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="b01c9-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="b01c9-116">Valor</span><span class="sxs-lookup"><span data-stu-id="b01c9-116">Value</span></span>|<span data-ttu-id="b01c9-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="b01c9-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="b01c9-118">El runtime usará comunicación remota entre límites de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b01c9-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="b01c9-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b01c9-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="b01c9-120">El tiempo de ejecución usará interoperabilidad COM en los límites del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b01c9-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b01c9-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b01c9-121">Child Elements</span></span>  
 <span data-ttu-id="b01c9-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b01c9-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b01c9-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b01c9-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b01c9-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="b01c9-124">Element</span></span>|<span data-ttu-id="b01c9-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="b01c9-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b01c9-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b01c9-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b01c9-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b01c9-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b01c9-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b01c9-128">Remarks</span></span>  
 <span data-ttu-id="b01c9-129">Al establecer el `enabled` atribuir a `true`, el tiempo de ejecución se comporta como sigue:</span><span class="sxs-lookup"><span data-stu-id="b01c9-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
-   <span data-ttu-id="b01c9-130">El runtime no llama a [IUnknown:: QueryInterface](http://go.microsoft.com/fwlink/?LinkID=144867) para un [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interfaz cuando una [IUnknown](http://go.microsoft.com/fwlink/?LinkId=148003) interfaz entra en el dominio a través de una interfaz COM.</span><span class="sxs-lookup"><span data-stu-id="b01c9-130">The runtime does not call [IUnknown::QueryInterface](http://go.microsoft.com/fwlink/?LinkID=144867) for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](http://go.microsoft.com/fwlink/?LinkId=148003) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="b01c9-131">En su lugar, construye un [contenedor RCW](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) alrededor del objeto.</span><span class="sxs-lookup"><span data-stu-id="b01c9-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
-   <span data-ttu-id="b01c9-132">El tiempo de ejecución devuelve E_NOINTERFACE cuando recibe un `QueryInterface` prevén un [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interfaz para cualquier [contenedor CCW](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW) que se ha creado en este dominio.</span><span class="sxs-lookup"><span data-stu-id="b01c9-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="b01c9-133">Estos dos comportamientos garantizan que todas las llamadas a través de COM interfaces entre objetos administrados a través del uso de los límites del dominio de aplicación COM y la interoperabilidad COM en lugar de comunicación remota.</span><span class="sxs-lookup"><span data-stu-id="b01c9-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b01c9-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b01c9-134">Example</span></span>  
 <span data-ttu-id="b01c9-135">En el ejemplo siguiente se muestra cómo especificar que el tiempo de ejecución debe utilizar COM interoperabilidad en los límites de aislamiento:</span><span class="sxs-lookup"><span data-stu-id="b01c9-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b01c9-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="b01c9-136">See Also</span></span>  
 [<span data-ttu-id="b01c9-137">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="b01c9-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="b01c9-138">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="b01c9-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
