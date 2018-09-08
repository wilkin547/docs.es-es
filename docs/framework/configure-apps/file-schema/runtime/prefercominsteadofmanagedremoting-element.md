---
title: '&lt;PreferComInsteadOfManagedRemoting&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c05e27226a58086c806e8977ba50a55873d1167e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44222667"
---
# <a name="ltprefercominsteadofmanagedremotinggt-element"></a><span data-ttu-id="689e3-102">&lt;PreferComInsteadOfManagedRemoting&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="689e3-102">&lt;PreferComInsteadOfManagedRemoting&gt; Element</span></span>
<span data-ttu-id="689e3-103">Especifica si el runtime usará interoperabilidad COM en lugar de comunicación remota para todas las llamadas entre los límites del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="689e3-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
 <span data-ttu-id="689e3-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="689e3-104">\<configuration></span></span>  
<span data-ttu-id="689e3-105">\<en tiempo de ejecución ></span><span class="sxs-lookup"><span data-stu-id="689e3-105">\<runtime></span></span>  
<span data-ttu-id="689e3-106">\<PreferComInsteadOfManagedRemoting ></span><span class="sxs-lookup"><span data-stu-id="689e3-106">\<PreferComInsteadOfManagedRemoting></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="689e3-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="689e3-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="689e3-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="689e3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="689e3-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="689e3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="689e3-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="689e3-110">Attributes</span></span>  
  
|<span data-ttu-id="689e3-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="689e3-111">Attribute</span></span>|<span data-ttu-id="689e3-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="689e3-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="689e3-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="689e3-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="689e3-114">Indica si el runtime usará interoperabilidad COM en lugar de comunicación remota entre límites de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="689e3-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="689e3-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="689e3-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="689e3-116">Valor</span><span class="sxs-lookup"><span data-stu-id="689e3-116">Value</span></span>|<span data-ttu-id="689e3-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="689e3-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="689e3-118">El tiempo de ejecución utilizará la comunicación remota entre límites de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="689e3-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="689e3-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="689e3-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="689e3-120">El runtime usará interoperabilidad COM en los límites del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="689e3-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="689e3-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="689e3-121">Child Elements</span></span>  
 <span data-ttu-id="689e3-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="689e3-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="689e3-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="689e3-123">Parent Elements</span></span>  
  
|<span data-ttu-id="689e3-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="689e3-124">Element</span></span>|<span data-ttu-id="689e3-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="689e3-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="689e3-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="689e3-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="689e3-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="689e3-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="689e3-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="689e3-128">Remarks</span></span>  
 <span data-ttu-id="689e3-129">Al establecer el `enabled` atributo `true`, el tiempo de ejecución se comporta como sigue:</span><span class="sxs-lookup"><span data-stu-id="689e3-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
-   <span data-ttu-id="689e3-130">El tiempo de ejecución no llama a [IUnknown:: QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) para un [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interfaz cuando una [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) interfaz entra en el dominio a través de una interfaz COM.</span><span class="sxs-lookup"><span data-stu-id="689e3-130">The runtime does not call [IUnknown::QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="689e3-131">En su lugar, construye un [contenedor RCW](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) alrededor del objeto.</span><span class="sxs-lookup"><span data-stu-id="689e3-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
-   <span data-ttu-id="689e3-132">El tiempo de ejecución devuelve E_NOINTERFACE cuando recibe un `QueryInterface` piden un [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interfaz para cualquier [contenedor CCW](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW) que se ha creado en este dominio.</span><span class="sxs-lookup"><span data-stu-id="689e3-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="689e3-133">Estos dos comportamientos garantizan que todas las llamadas a través de COM interfaces entre los objetos administrados a través del uso de los límites del dominio de aplicación COM y la interoperabilidad COM en lugar de comunicación remota.</span><span class="sxs-lookup"><span data-stu-id="689e3-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="689e3-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="689e3-134">Example</span></span>  
 <span data-ttu-id="689e3-135">El ejemplo siguiente muestra cómo especificar que el runtime debe usar COM interoperabilidad entre los límites de aislamiento:</span><span class="sxs-lookup"><span data-stu-id="689e3-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="689e3-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="689e3-136">See Also</span></span>  
 [<span data-ttu-id="689e3-137">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="689e3-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="689e3-138">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="689e3-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
