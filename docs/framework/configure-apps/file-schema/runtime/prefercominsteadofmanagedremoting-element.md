---
title: <PreferComInsteadOfManagedRemoting> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e32e4b490f0824cf97a1ae5910d7c74801c7b439
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592690"
---
# <a name="prefercominsteadofmanagedremoting-element"></a><span data-ttu-id="c46b1-102">\<PreferComInsteadOfManagedRemoting > elemento</span><span class="sxs-lookup"><span data-stu-id="c46b1-102">\<PreferComInsteadOfManagedRemoting> Element</span></span>
<span data-ttu-id="c46b1-103">Especifica si el runtime usará interoperabilidad COM en lugar de comunicación remota para todas las llamadas entre los límites del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="c46b1-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
 <span data-ttu-id="c46b1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c46b1-104">\<configuration></span></span>  
<span data-ttu-id="c46b1-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="c46b1-105">\<runtime></span></span>  
<span data-ttu-id="c46b1-106">\<PreferComInsteadOfManagedRemoting></span><span class="sxs-lookup"><span data-stu-id="c46b1-106">\<PreferComInsteadOfManagedRemoting></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c46b1-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c46b1-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c46b1-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c46b1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c46b1-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c46b1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c46b1-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="c46b1-110">Attributes</span></span>  
  
|<span data-ttu-id="c46b1-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="c46b1-111">Attribute</span></span>|<span data-ttu-id="c46b1-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c46b1-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="c46b1-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="c46b1-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="c46b1-114">Indica si el runtime usará interoperabilidad COM en lugar de comunicación remota entre límites de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="c46b1-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="c46b1-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="c46b1-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="c46b1-116">Valor</span><span class="sxs-lookup"><span data-stu-id="c46b1-116">Value</span></span>|<span data-ttu-id="c46b1-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="c46b1-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="c46b1-118">El tiempo de ejecución utilizará la comunicación remota entre límites de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="c46b1-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="c46b1-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c46b1-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="c46b1-120">El runtime usará interoperabilidad COM en los límites del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="c46b1-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c46b1-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c46b1-121">Child Elements</span></span>  
 <span data-ttu-id="c46b1-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c46b1-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c46b1-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c46b1-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c46b1-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="c46b1-124">Element</span></span>|<span data-ttu-id="c46b1-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="c46b1-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c46b1-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c46b1-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c46b1-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c46b1-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c46b1-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c46b1-128">Remarks</span></span>  
 <span data-ttu-id="c46b1-129">Al establecer el `enabled` atributo `true`, el tiempo de ejecución se comporta como sigue:</span><span class="sxs-lookup"><span data-stu-id="c46b1-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
- <span data-ttu-id="c46b1-130">El tiempo de ejecución no llama a [IUnknown:: QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) para un [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interfaz cuando una [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) interfaz entra en el dominio a través de una interfaz COM.</span><span class="sxs-lookup"><span data-stu-id="c46b1-130">The runtime does not call [IUnknown::QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="c46b1-131">En su lugar, construye un [contenedor RCW](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) alrededor del objeto.</span><span class="sxs-lookup"><span data-stu-id="c46b1-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
- <span data-ttu-id="c46b1-132">El tiempo de ejecución devuelve E_NOINTERFACE cuando recibe un `QueryInterface` piden un [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interfaz para cualquier [contenedor CCW](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW) que se ha creado en este dominio.</span><span class="sxs-lookup"><span data-stu-id="c46b1-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="c46b1-133">Estos dos comportamientos garantizan que todas las llamadas a través de COM interfaces entre los objetos administrados a través del uso de los límites del dominio de aplicación COM y la interoperabilidad COM en lugar de comunicación remota.</span><span class="sxs-lookup"><span data-stu-id="c46b1-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c46b1-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c46b1-134">Example</span></span>  
 <span data-ttu-id="c46b1-135">El ejemplo siguiente muestra cómo especificar que el runtime debe usar COM interoperabilidad entre los límites de aislamiento:</span><span class="sxs-lookup"><span data-stu-id="c46b1-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c46b1-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="c46b1-136">See also</span></span>

- [<span data-ttu-id="c46b1-137">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="c46b1-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="c46b1-138">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="c46b1-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
