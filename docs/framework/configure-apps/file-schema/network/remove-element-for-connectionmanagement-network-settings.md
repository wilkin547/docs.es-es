---
title: "&lt;quitar&gt; elemento para connectionManagement (configuración de red)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- connectionManagement, remove element
- <remove> element, connectionManagement
- <connectionManagement>, remove element
- remove element, connectionManagement
ms.assetid: 94b81775-5a22-4975-8c47-8620c40c3f35
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 92536ad7605211f3a7f606920b054a217427c8f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltremovegt-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="33c0f-102">&lt;quitar&gt; elemento para connectionManagement (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="33c0f-102">&lt;remove&gt; Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="33c0f-103">Quita una dirección IP o nombre DNS de la lista de administración de conexiones.</span><span class="sxs-lookup"><span data-stu-id="33c0f-103">Removes an IP address or DNS name from the connection management list.</span></span>  
  
 <span data-ttu-id="33c0f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="33c0f-104">\<configuration></span></span>  
<span data-ttu-id="33c0f-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="33c0f-105">\<system.net></span></span>  
<span data-ttu-id="33c0f-106">\<connectionManagement ></span><span class="sxs-lookup"><span data-stu-id="33c0f-106">\<connectionManagement></span></span>  
<span data-ttu-id="33c0f-107">\<Quitar ></span><span class="sxs-lookup"><span data-stu-id="33c0f-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33c0f-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33c0f-108">Syntax</span></span>  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33c0f-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="33c0f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="33c0f-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="33c0f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33c0f-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="33c0f-111">Attributes</span></span>  
  
|<span data-ttu-id="33c0f-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="33c0f-112">**Attribute**</span></span>|<span data-ttu-id="33c0f-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="33c0f-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="33c0f-114">Una dirección IP o nombre DNS.</span><span class="sxs-lookup"><span data-stu-id="33c0f-114">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="33c0f-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="33c0f-115">Child Elements</span></span>  
 <span data-ttu-id="33c0f-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="33c0f-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="33c0f-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="33c0f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="33c0f-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="33c0f-118">**Element**</span></span>|<span data-ttu-id="33c0f-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="33c0f-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="33c0f-120">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="33c0f-120">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="33c0f-121">Especifica el número máximo de conexiones a un host de red.</span><span class="sxs-lookup"><span data-stu-id="33c0f-121">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33c0f-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="33c0f-122">Remarks</span></span>  
 <span data-ttu-id="33c0f-123">El `remove` elemento quita la entrada de lista de administración de conexión para el servidor especificado.</span><span class="sxs-lookup"><span data-stu-id="33c0f-123">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="33c0f-124">El valor de la `address` atributo debe ser un nombre de host o dirección IP válido.</span><span class="sxs-lookup"><span data-stu-id="33c0f-124">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="33c0f-125">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="33c0f-125">Configuration Files</span></span>  
 <span data-ttu-id="33c0f-126">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="33c0f-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="33c0f-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="33c0f-127">Example</span></span>  
 <span data-ttu-id="33c0f-128">En el ejemplo siguiente se quita las entradas de lista de administración de conexión para el servidor www.adventure-works.com y, a continuación, configura una aplicación para usar cuatro conexiones con el servidor www.contoso.com y dos conexiones con todos los demás servidores.</span><span class="sxs-lookup"><span data-stu-id="33c0f-128">The following example removes any connection management list entries for the server www.adventure-works.com and then configures an application to use four connections to the server www.contoso.com and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <remove address="http://www.adventure-works.com" />  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="33c0f-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="33c0f-129">See Also</span></span>  
 <xref:System.Net.ServicePoint>  
 <xref:System.Net.ServicePointManager>  
 [<span data-ttu-id="33c0f-130">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="33c0f-130">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
