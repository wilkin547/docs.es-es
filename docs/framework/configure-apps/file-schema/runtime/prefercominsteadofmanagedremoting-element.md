---
title: <PreferComInsteadOfManagedRemoting> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
ms.openlocfilehash: 1376df4efd56734f2b8da9bd76033afcce8a285b
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452258"
---
# <a name="prefercominsteadofmanagedremoting-element"></a><span data-ttu-id="6b07c-102">\<elemento > PreferComInsteadOfManagedRemoting</span><span class="sxs-lookup"><span data-stu-id="6b07c-102">\<PreferComInsteadOfManagedRemoting> Element</span></span>
<span data-ttu-id="6b07c-103">Especifica si el tiempo de ejecución usará la interoperabilidad COM en lugar de la comunicación remota para todas las llamadas en los límites del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="6b07c-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
<span data-ttu-id="6b07c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6b07c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6b07c-105">&nbsp;&nbsp;[ **\<en tiempo de ejecución >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="6b07c-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="6b07c-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<PreferComInsteadOfManagedRemoting >**</span><span class="sxs-lookup"><span data-stu-id="6b07c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<PreferComInsteadOfManagedRemoting>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b07c-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6b07c-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b07c-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6b07c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6b07c-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6b07c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b07c-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="6b07c-110">Attributes</span></span>  
  
|<span data-ttu-id="6b07c-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="6b07c-111">Attribute</span></span>|<span data-ttu-id="6b07c-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b07c-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="6b07c-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="6b07c-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="6b07c-114">Indica si el tiempo de ejecución utilizará la interoperabilidad COM en lugar de la comunicación remota entre los límites del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="6b07c-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="6b07c-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="6b07c-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="6b07c-116">Value</span><span class="sxs-lookup"><span data-stu-id="6b07c-116">Value</span></span>|<span data-ttu-id="6b07c-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b07c-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="6b07c-118">El Runtime usará la comunicación remota en los límites del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="6b07c-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="6b07c-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6b07c-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="6b07c-120">El Runtime usará la interoperabilidad COM en los límites del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="6b07c-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6b07c-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6b07c-121">Child Elements</span></span>  
 <span data-ttu-id="6b07c-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6b07c-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6b07c-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6b07c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="6b07c-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="6b07c-124">Element</span></span>|<span data-ttu-id="6b07c-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b07c-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6b07c-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6b07c-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="6b07c-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="6b07c-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b07c-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6b07c-128">Remarks</span></span>  
 <span data-ttu-id="6b07c-129">Al establecer el atributo `enabled` en `true`, el tiempo de ejecución se comporta de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="6b07c-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
- <span data-ttu-id="6b07c-130">El runtime no llama a [IUnknown:: QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) para una interfaz [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) cuando una interfaz [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) entra en el dominio a través de una interfaz com.</span><span class="sxs-lookup"><span data-stu-id="6b07c-130">The runtime does not call [IUnknown::QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="6b07c-131">En su lugar, crea un contenedor RCW ( [Runtime Callable wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) ) alrededor del objeto.</span><span class="sxs-lookup"><span data-stu-id="6b07c-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
- <span data-ttu-id="6b07c-132">El tiempo de ejecución devuelve E_NOINTERFACE cuando recibe una llamada `QueryInterface` para una interfaz [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) para cualquier contenedor CCW ( [com Callable wrapper](../../../../standard/native-interop/com-callable-wrapper.md) ) que se ha creado en este dominio.</span><span class="sxs-lookup"><span data-stu-id="6b07c-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../standard/native-interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="6b07c-133">Estos dos comportamientos garantizan que todas las llamadas a través de interfaces COM entre los objetos administrados a través de los límites del dominio de aplicación utilizan la interoperabilidad com y COM en lugar de la comunicación remota.</span><span class="sxs-lookup"><span data-stu-id="6b07c-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b07c-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b07c-134">Example</span></span>  
 <span data-ttu-id="6b07c-135">En el ejemplo siguiente se muestra cómo especificar que el Runtime debe utilizar la interoperabilidad COM en los límites de aislamiento:</span><span class="sxs-lookup"><span data-stu-id="6b07c-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6b07c-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6b07c-136">See also</span></span>

- [<span data-ttu-id="6b07c-137">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="6b07c-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="6b07c-138">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="6b07c-138">Configuration File Schema</span></span>](../index.md)
