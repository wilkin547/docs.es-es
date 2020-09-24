---
title: Elemento <connectionManagement> (configuración de red)
description: El <connectionManagement> elemento de configuración de red especifica el número máximo de conexiones a un host de red en el .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement
- http://schemas.microsoft.com/.NetConfiguration/v2.0#connectionManagement
helpviewer_keywords:
- <connectionManagement> element
- connectionManagement element
ms.assetid: bedccaab-12a2-4511-8f67-e961f249aec6
ms.openlocfilehash: 52b780c739a00cb53694b547ee1a33c1b5d98c86
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167319"
---
# <a name="connectionmanagement-element-network-settings"></a><span data-ttu-id="9466a-103">Elemento \<connectionManagement> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="9466a-103">\<connectionManagement> Element (Network Settings)</span></span>

<span data-ttu-id="9466a-104">Especifica el número máximo de conexiones a un host de red.</span><span class="sxs-lookup"><span data-stu-id="9466a-104">Specifies the maximum number of connections to a network host.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionManagement>**

## <a name="syntax"></a><span data-ttu-id="9466a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9466a-105">Syntax</span></span>  
  
```xml  
<connectionManagement>
</connectionManagement>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9466a-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9466a-106">Attributes and Elements</span></span>  

 <span data-ttu-id="9466a-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9466a-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9466a-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="9466a-108">Attributes</span></span>  

 <span data-ttu-id="9466a-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9466a-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9466a-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9466a-110">Child Elements</span></span>  
  
|<span data-ttu-id="9466a-111">**Element**</span><span class="sxs-lookup"><span data-stu-id="9466a-111">**Element**</span></span>|<span data-ttu-id="9466a-112">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="9466a-112">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="9466a-113">add</span><span class="sxs-lookup"><span data-stu-id="9466a-113">add</span></span>](add-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="9466a-114">Agrega una dirección IP o nombre DNS a la lista de administración de conexión.</span><span class="sxs-lookup"><span data-stu-id="9466a-114">Adds an IP address or DNS name to the connection management list.</span></span>|  
|[<span data-ttu-id="9466a-115">clear</span><span class="sxs-lookup"><span data-stu-id="9466a-115">clear</span></span>](clear-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="9466a-116">Borra la lista de administración de conexiones.</span><span class="sxs-lookup"><span data-stu-id="9466a-116">Clears the connection management list.</span></span>|  
|[<span data-ttu-id="9466a-117">remove</span><span class="sxs-lookup"><span data-stu-id="9466a-117">remove</span></span>](remove-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="9466a-118">Quita una dirección IP o un nombre DNS de la lista de administración de conexiones.</span><span class="sxs-lookup"><span data-stu-id="9466a-118">Removes an IP address or DNS name from the connection management list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9466a-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9466a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="9466a-120">**Element**</span><span class="sxs-lookup"><span data-stu-id="9466a-120">**Element**</span></span>|<span data-ttu-id="9466a-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="9466a-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="9466a-122">system.net</span><span class="sxs-lookup"><span data-stu-id="9466a-122">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="9466a-123">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="9466a-123">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9466a-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9466a-124">Remarks</span></span>  

 <span data-ttu-id="9466a-125">El `connectionManagement` elemento define el número máximo de conexiones a un servidor o grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="9466a-125">The `connectionManagement` element defines the maximum number of connections to a server or group of servers.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="9466a-126">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="9466a-126">Configuration Files</span></span>  

 <span data-ttu-id="9466a-127">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="9466a-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9466a-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9466a-128">Example</span></span>  

 <span data-ttu-id="9466a-129">En el ejemplo siguiente se configura una aplicación para que use cuatro conexiones al servidor `www.contoso.com` y dos conexiones a todos los demás servidores.</span><span class="sxs-lookup"><span data-stu-id="9466a-129">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9466a-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9466a-130">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="9466a-131">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="9466a-131">Network Settings Schema</span></span>](index.md)
