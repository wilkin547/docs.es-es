---
title: Elemento <module> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#module
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/module
helpviewer_keywords:
- module element
- <module> element
ms.assetid: 10318725-9666-4d65-ab61-b94c64e59f13
ms.openlocfilehash: 851a63b41dfb5d3b4058e1373148f48d47d9d6ae
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664067"
---
# <a name="module-element-network-settings"></a><span data-ttu-id="bffff-102">\<Module > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="bffff-102">\<module> Element (Network Settings)</span></span>
<span data-ttu-id="bffff-103">Agrega un nuevo módulo proxy a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bffff-103">Adds a new proxy module to the application.</span></span>  
  
 <span data-ttu-id="bffff-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bffff-104">\<configuration></span></span>  
<span data-ttu-id="bffff-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="bffff-105">\<system.net></span></span>  
<span data-ttu-id="bffff-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="bffff-106">\<defaultProxy></span></span>  
<span data-ttu-id="bffff-107">\<module></span><span class="sxs-lookup"><span data-stu-id="bffff-107">\<module></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bffff-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bffff-108">Syntax</span></span>  
  
```xml  
<module   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bffff-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bffff-109">Attributes and Elements</span></span>  
 <span data-ttu-id="bffff-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bffff-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bffff-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="bffff-111">Attributes</span></span>  
  
|<span data-ttu-id="bffff-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="bffff-112">**Attribute**</span></span>|<span data-ttu-id="bffff-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="bffff-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="bffff-114">El nombre de tipo completo (indicado por la <xref:System.Type.FullName%2A> propiedad) y el nombre de ensamblado (indicado <xref:System.Reflection.Assembly.FullName%2A> por la propiedad), separados por una coma, que implementa el proxy.</span><span class="sxs-lookup"><span data-stu-id="bffff-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bffff-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bffff-115">Child Elements</span></span>  
 <span data-ttu-id="bffff-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bffff-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bffff-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bffff-117">Parent Elements</span></span>  
  
|<span data-ttu-id="bffff-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="bffff-118">**Element**</span></span>|<span data-ttu-id="bffff-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="bffff-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="bffff-120">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="bffff-120">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="bffff-121">Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).</span><span class="sxs-lookup"><span data-stu-id="bffff-121">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bffff-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bffff-122">Remarks</span></span>  
 <span data-ttu-id="bffff-123">El `module` elemento registra las clases de proxy que implementan la <xref:System.Net.IWebProxy> interfaz.</span><span class="sxs-lookup"><span data-stu-id="bffff-123">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="bffff-124">Después de registrar la clase de proxy `module` , se puede usar para solicitar información a través del proxy admitido.</span><span class="sxs-lookup"><span data-stu-id="bffff-124">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="bffff-125">El valor `type` del atributo debe ser el nombre de clase del módulo y el nombre de su biblioteca de vínculos dinámicos (dll) correspondiente.</span><span class="sxs-lookup"><span data-stu-id="bffff-125">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="bffff-126">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="bffff-126">Configuration Files</span></span>  
 <span data-ttu-id="bffff-127">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="bffff-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bffff-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bffff-128">Example</span></span>  
 <span data-ttu-id="bffff-129">En el ejemplo siguiente se registra una clase de proxy personalizada.</span><span class="sxs-lookup"><span data-stu-id="bffff-129">The following example registers a custom proxy class.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bffff-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="bffff-130">See also</span></span>

- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="bffff-131">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="bffff-131">Network Settings Schema</span></span>](index.md)
