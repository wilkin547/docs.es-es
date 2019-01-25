---
title: '&lt;connectionManagement&gt; elemento (configuración de red)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement
- http://schemas.microsoft.com/.NetConfiguration/v2.0#connectionManagement
helpviewer_keywords:
- <connectionManagement> element
- connectionManagement element
ms.assetid: bedccaab-12a2-4511-8f67-e961f249aec6
ms.openlocfilehash: 28864de79e809968f7efa6f3b052cfd599961854
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685031"
---
# <a name="ltconnectionmanagementgt-element-network-settings"></a><span data-ttu-id="18668-102">&lt;connectionManagement&gt; elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="18668-102">&lt;connectionManagement&gt; Element (Network Settings)</span></span>
<span data-ttu-id="18668-103">Especifica el número máximo de conexiones a un host de red.</span><span class="sxs-lookup"><span data-stu-id="18668-103">Specifies the maximum number of connections to a network host.</span></span>  
  
 <span data-ttu-id="18668-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="18668-104">\<configuration></span></span>  
<span data-ttu-id="18668-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="18668-105">\<system.net></span></span>  
<span data-ttu-id="18668-106">\<connectionManagement></span><span class="sxs-lookup"><span data-stu-id="18668-106">\<connectionManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18668-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="18668-107">Syntax</span></span>  
  
```xml  
<connectionManagement>   
</connectionManagement>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18668-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="18668-108">Attributes and Elements</span></span>  
 <span data-ttu-id="18668-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="18668-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18668-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="18668-110">Attributes</span></span>  
 <span data-ttu-id="18668-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="18668-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="18668-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="18668-112">Child Elements</span></span>  
  
|<span data-ttu-id="18668-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="18668-113">**Element**</span></span>|<span data-ttu-id="18668-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="18668-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="18668-115">add</span><span class="sxs-lookup"><span data-stu-id="18668-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="18668-116">Agrega una dirección IP o nombre DNS a la lista de administración de conexión.</span><span class="sxs-lookup"><span data-stu-id="18668-116">Adds an IP address or DNS name to the connection management list.</span></span>|  
|[<span data-ttu-id="18668-117">clear</span><span class="sxs-lookup"><span data-stu-id="18668-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="18668-118">Borra la lista de administración de conexiones.</span><span class="sxs-lookup"><span data-stu-id="18668-118">Clears the connection management list.</span></span>|  
|[<span data-ttu-id="18668-119">remove</span><span class="sxs-lookup"><span data-stu-id="18668-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="18668-120">Quita una dirección IP o nombre DNS de la lista de administración de conexiones.</span><span class="sxs-lookup"><span data-stu-id="18668-120">Removes an IP address or DNS name from the connection management list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="18668-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="18668-121">Parent Elements</span></span>  
  
|<span data-ttu-id="18668-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="18668-122">**Element**</span></span>|<span data-ttu-id="18668-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="18668-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="18668-124">system.net</span><span class="sxs-lookup"><span data-stu-id="18668-124">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="18668-125">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="18668-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18668-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="18668-126">Remarks</span></span>  
 <span data-ttu-id="18668-127">El `connectionManagement` elemento define el número máximo de conexiones en un servidor o grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="18668-127">The `connectionManagement` element defines the maximum number of connections to a server or group of servers.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="18668-128">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="18668-128">Configuration Files</span></span>  
 <span data-ttu-id="18668-129">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="18668-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="18668-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="18668-130">Example</span></span>  
 <span data-ttu-id="18668-131">En el ejemplo siguiente se configura una aplicación para usar cuatro conexiones al servidor `www.contoso.com` y dos conexiones con todos los demás servidores.</span><span class="sxs-lookup"><span data-stu-id="18668-131">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="18668-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="18668-132">See also</span></span>
- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="18668-133">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="18668-133">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
