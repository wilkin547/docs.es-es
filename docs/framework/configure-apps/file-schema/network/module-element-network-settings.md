---
title: "&lt;módulo&gt; Element (Network Settings)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#module
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/module
helpviewer_keywords:
- module element
- <module> element
ms.assetid: 10318725-9666-4d65-ab61-b94c64e59f13
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 25c5e4fe37d2895bcd891bb2ebf2f80ae8f10a7d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltmodulegt-element-network-settings"></a><span data-ttu-id="4d355-102">&lt;módulo&gt; Element (Network Settings)</span><span class="sxs-lookup"><span data-stu-id="4d355-102">&lt;module&gt; Element (Network Settings)</span></span>
<span data-ttu-id="4d355-103">Agrega un nuevo módulo proxy a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4d355-103">Adds a new proxy module to the application.</span></span>  
  
 <span data-ttu-id="4d355-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4d355-104">\<configuration></span></span>  
<span data-ttu-id="4d355-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="4d355-105">\<system.net></span></span>  
<span data-ttu-id="4d355-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="4d355-106">\<defaultProxy></span></span>  
<span data-ttu-id="4d355-107">\<módulo ></span><span class="sxs-lookup"><span data-stu-id="4d355-107">\<module></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d355-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d355-108">Syntax</span></span>  
  
```xml  
<module   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d355-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4d355-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4d355-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4d355-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d355-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="4d355-111">Attributes</span></span>  
  
|<span data-ttu-id="4d355-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="4d355-112">**Attribute**</span></span>|<span data-ttu-id="4d355-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="4d355-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="4d355-114">El nombre de tipo completo (indicado por la <xref:System.Type.FullName%2A> propiedad) y el nombre del ensamblado (indicado por el <xref:System.Reflection.Assembly.FullName%2A> propiedad), separados por comas, que implementa el proxy.</span><span class="sxs-lookup"><span data-stu-id="4d355-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4d355-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4d355-115">Child Elements</span></span>  
 <span data-ttu-id="4d355-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4d355-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4d355-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4d355-117">Parent Elements</span></span>  
  
|<span data-ttu-id="4d355-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="4d355-118">**Element**</span></span>|<span data-ttu-id="4d355-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="4d355-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4d355-120">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="4d355-120">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="4d355-121">Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).</span><span class="sxs-lookup"><span data-stu-id="4d355-121">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d355-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4d355-122">Remarks</span></span>  
 <span data-ttu-id="4d355-123">El `module` elemento registra clases de proxy que implementan la <xref:System.Net.IWebProxy> interfaz.</span><span class="sxs-lookup"><span data-stu-id="4d355-123">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="4d355-124">Después de registrar la clase de proxy, `module` puede utilizarse para solicitar información a través del proxy compatible.</span><span class="sxs-lookup"><span data-stu-id="4d355-124">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="4d355-125">El valor de la `type` atributo debe ser el nombre de clase del módulo y el nombre de su biblioteca de vínculos dinámicos (DLL) correspondiente.</span><span class="sxs-lookup"><span data-stu-id="4d355-125">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4d355-126">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="4d355-126">Configuration Files</span></span>  
 <span data-ttu-id="4d355-127">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="4d355-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d355-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4d355-128">Example</span></span>  
 <span data-ttu-id="4d355-129">El ejemplo siguiente registra una clase de proxy personalizada.</span><span class="sxs-lookup"><span data-stu-id="4d355-129">The following example registers a custom proxy class.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4d355-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d355-130">See Also</span></span>  
 <xref:System.Net.IWebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="4d355-131">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="4d355-131">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
