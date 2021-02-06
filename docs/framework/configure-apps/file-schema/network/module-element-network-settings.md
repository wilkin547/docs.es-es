---
description: 'Más información acerca de: <module> elemento (configuración de red)'
title: Elemento <module> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#module
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/module
helpviewer_keywords:
- module element
- <module> element
ms.assetid: 10318725-9666-4d65-ab61-b94c64e59f13
ms.openlocfilehash: d498b79ae6046367bc81add5ea387e178ab6c29d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652840"
---
# <a name="module-element-network-settings"></a><span data-ttu-id="6729e-103">Elemento \<module> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="6729e-103">\<module> Element (Network Settings)</span></span>

<span data-ttu-id="6729e-104">Agrega un nuevo módulo proxy a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6729e-104">Adds a new proxy module to the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<module>**

## <a name="syntax"></a><span data-ttu-id="6729e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6729e-105">Syntax</span></span>  
  
```xml  
<module
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6729e-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6729e-106">Attributes and Elements</span></span>  

 <span data-ttu-id="6729e-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6729e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6729e-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="6729e-108">Attributes</span></span>  
  
|<span data-ttu-id="6729e-109">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="6729e-109">**Attribute**</span></span>|<span data-ttu-id="6729e-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="6729e-110">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="6729e-111">El nombre de tipo completo (indicado por la <xref:System.Type.FullName%2A> propiedad) y el nombre de ensamblado (indicado por la <xref:System.Reflection.Assembly.FullName%2A> propiedad), separados por una coma, que implementa el proxy.</span><span class="sxs-lookup"><span data-stu-id="6729e-111">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6729e-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6729e-112">Child Elements</span></span>  

 <span data-ttu-id="6729e-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6729e-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6729e-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6729e-114">Parent Elements</span></span>  
  
|<span data-ttu-id="6729e-115">**Element**</span><span class="sxs-lookup"><span data-stu-id="6729e-115">**Element**</span></span>|<span data-ttu-id="6729e-116">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="6729e-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="6729e-117">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="6729e-117">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="6729e-118">Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).</span><span class="sxs-lookup"><span data-stu-id="6729e-118">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6729e-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6729e-119">Remarks</span></span>  

 <span data-ttu-id="6729e-120">El `module` elemento registra las clases de proxy que implementan la <xref:System.Net.IWebProxy> interfaz.</span><span class="sxs-lookup"><span data-stu-id="6729e-120">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="6729e-121">Después de registrar la clase de proxy, `module` se puede usar para solicitar información a través del proxy admitido.</span><span class="sxs-lookup"><span data-stu-id="6729e-121">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="6729e-122">El valor del `type` atributo debe ser el nombre de clase del módulo y el nombre de su biblioteca de vínculos dinámicos (dll) correspondiente.</span><span class="sxs-lookup"><span data-stu-id="6729e-122">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="6729e-123">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="6729e-123">Configuration Files</span></span>  

 <span data-ttu-id="6729e-124">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="6729e-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6729e-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6729e-125">Example</span></span>  

 <span data-ttu-id="6729e-126">En el ejemplo siguiente se registra una clase de proxy personalizada.</span><span class="sxs-lookup"><span data-stu-id="6729e-126">The following example registers a custom proxy class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <module  
        type="Test.CustomWebProxy, TestProxy, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b23a5c561934e385"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6729e-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="6729e-127">See also</span></span>

- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="6729e-128">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="6729e-128">Network Settings Schema</span></span>](index.md)
