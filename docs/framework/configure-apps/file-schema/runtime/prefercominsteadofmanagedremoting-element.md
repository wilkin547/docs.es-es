---
description: 'Más información acerca de: <PreferComInsteadOfManagedRemoting> elemento'
title: <PreferComInsteadOfManagedRemoting> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
ms.openlocfilehash: b621af9b584d1ea2623ffe5a44f74b5b7bd520e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782278"
---
# <a name="prefercominsteadofmanagedremoting-element"></a><span data-ttu-id="93ab1-103">\<PreferComInsteadOfManagedRemoting> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="93ab1-103">\<PreferComInsteadOfManagedRemoting> Element</span></span>

<span data-ttu-id="93ab1-104">Especifica si el tiempo de ejecución usará la interoperabilidad COM en lugar de la comunicación remota para todas las llamadas en los límites del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="93ab1-104">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<PreferComInsteadOfManagedRemoting>**  
  
## <a name="syntax"></a><span data-ttu-id="93ab1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="93ab1-105">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93ab1-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="93ab1-106">Attributes and Elements</span></span>  

 <span data-ttu-id="93ab1-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="93ab1-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93ab1-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="93ab1-108">Attributes</span></span>  
  
|<span data-ttu-id="93ab1-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="93ab1-109">Attribute</span></span>|<span data-ttu-id="93ab1-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="93ab1-110">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="93ab1-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="93ab1-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="93ab1-112">Indica si el tiempo de ejecución utilizará la interoperabilidad COM en lugar de la comunicación remota entre los límites del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="93ab1-112">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="93ab1-113">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="93ab1-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="93ab1-114">Value</span><span class="sxs-lookup"><span data-stu-id="93ab1-114">Value</span></span>|<span data-ttu-id="93ab1-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="93ab1-115">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="93ab1-116">El Runtime usará la comunicación remota en los límites del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="93ab1-116">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="93ab1-117">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="93ab1-117">This is the default.</span></span>|  
|`true`|<span data-ttu-id="93ab1-118">El Runtime usará la interoperabilidad COM en los límites del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="93ab1-118">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="93ab1-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="93ab1-119">Child Elements</span></span>  

 <span data-ttu-id="93ab1-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="93ab1-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="93ab1-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="93ab1-121">Parent Elements</span></span>  
  
|<span data-ttu-id="93ab1-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="93ab1-122">Element</span></span>|<span data-ttu-id="93ab1-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="93ab1-123">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="93ab1-124">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="93ab1-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="93ab1-125">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="93ab1-125">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93ab1-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="93ab1-126">Remarks</span></span>  

 <span data-ttu-id="93ab1-127">Al establecer el `enabled` atributo en `true` , el tiempo de ejecución se comporta de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="93ab1-127">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
- <span data-ttu-id="93ab1-128">El runtime no llama a [IUnknown:: QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) para una interfaz [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) cuando una interfaz [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) entra en el dominio a través de una interfaz com.</span><span class="sxs-lookup"><span data-stu-id="93ab1-128">The runtime does not call [IUnknown::QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="93ab1-129">En su lugar, crea un contenedor RCW ( [Runtime Callable wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) ) alrededor del objeto.</span><span class="sxs-lookup"><span data-stu-id="93ab1-129">Instead, it constructs a [Runtime Callable Wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
- <span data-ttu-id="93ab1-130">El tiempo de ejecución devuelve E_NOINTERFACE cuando recibe una `QueryInterface` llamada a una interfaz [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) para cualquier contenedor CCW ( [com Callable wrapper](../../../../standard/native-interop/com-callable-wrapper.md) ) que se ha creado en este dominio.</span><span class="sxs-lookup"><span data-stu-id="93ab1-130">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../standard/native-interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="93ab1-131">Estos dos comportamientos garantizan que todas las llamadas a través de interfaces COM entre los objetos administrados a través de los límites del dominio de aplicación utilizan la interoperabilidad com y COM en lugar de la comunicación remota.</span><span class="sxs-lookup"><span data-stu-id="93ab1-131">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93ab1-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="93ab1-132">Example</span></span>  

 <span data-ttu-id="93ab1-133">En el ejemplo siguiente se muestra cómo especificar que el Runtime debe utilizar la interoperabilidad COM en los límites de aislamiento:</span><span class="sxs-lookup"><span data-stu-id="93ab1-133">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="93ab1-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="93ab1-134">See also</span></span>

- [<span data-ttu-id="93ab1-135">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="93ab1-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="93ab1-136">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="93ab1-136">Configuration File Schema</span></span>](../index.md)
