---
title: Elemento <connectionManagement> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement
- http://schemas.microsoft.com/.NetConfiguration/v2.0#connectionManagement
helpviewer_keywords:
- <connectionManagement> element
- connectionManagement element
ms.assetid: bedccaab-12a2-4511-8f67-e961f249aec6
ms.openlocfilehash: 9f1e382bbbaad2cb95e2c33bbbdfb4c505378c9e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154899"
---
# <a name="connectionmanagement-element-network-settings"></a><span data-ttu-id="bede3-102">Elemento \<connectionManagement> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="bede3-102">\<connectionManagement> Element (Network Settings)</span></span>
<span data-ttu-id="bede3-103">Especifica el número máximo de conexiones a un host de red.</span><span class="sxs-lookup"><span data-stu-id="bede3-103">Specifies the maximum number of connections to a network host.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionManagement>**

## <a name="syntax"></a><span data-ttu-id="bede3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bede3-104">Syntax</span></span>  
  
```xml  
<connectionManagement>
</connectionManagement>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bede3-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bede3-105">Attributes and Elements</span></span>  
 <span data-ttu-id="bede3-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bede3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bede3-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="bede3-107">Attributes</span></span>  
 <span data-ttu-id="bede3-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bede3-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bede3-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bede3-109">Child Elements</span></span>  
  
|<span data-ttu-id="bede3-110">**Element**</span><span class="sxs-lookup"><span data-stu-id="bede3-110">**Element**</span></span>|<span data-ttu-id="bede3-111">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="bede3-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="bede3-112">add</span><span class="sxs-lookup"><span data-stu-id="bede3-112">add</span></span>](add-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="bede3-113">Agrega una dirección IP o nombre DNS a la lista de administración de conexión.</span><span class="sxs-lookup"><span data-stu-id="bede3-113">Adds an IP address or DNS name to the connection management list.</span></span>|  
|[<span data-ttu-id="bede3-114">clear</span><span class="sxs-lookup"><span data-stu-id="bede3-114">clear</span></span>](clear-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="bede3-115">Borra la lista de administración de conexiones.</span><span class="sxs-lookup"><span data-stu-id="bede3-115">Clears the connection management list.</span></span>|  
|[<span data-ttu-id="bede3-116">remove</span><span class="sxs-lookup"><span data-stu-id="bede3-116">remove</span></span>](remove-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="bede3-117">Quita una dirección IP o un nombre DNS de la lista de administración de conexiones.</span><span class="sxs-lookup"><span data-stu-id="bede3-117">Removes an IP address or DNS name from the connection management list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bede3-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bede3-118">Parent Elements</span></span>  
  
|<span data-ttu-id="bede3-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="bede3-119">**Element**</span></span>|<span data-ttu-id="bede3-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="bede3-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="bede3-121">system.net</span><span class="sxs-lookup"><span data-stu-id="bede3-121">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="bede3-122">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="bede3-122">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bede3-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bede3-123">Remarks</span></span>  
 <span data-ttu-id="bede3-124">El `connectionManagement` elemento define el número máximo de conexiones a un servidor o grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="bede3-124">The `connectionManagement` element defines the maximum number of connections to a server or group of servers.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="bede3-125">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="bede3-125">Configuration Files</span></span>  
 <span data-ttu-id="bede3-126">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="bede3-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bede3-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bede3-127">Example</span></span>  
 <span data-ttu-id="bede3-128">En el ejemplo siguiente se configura una aplicación para que use cuatro conexiones al servidor `www.contoso.com` y dos conexiones a todos los demás servidores.</span><span class="sxs-lookup"><span data-stu-id="bede3-128">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bede3-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bede3-129">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="bede3-130">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="bede3-130">Network Settings Schema</span></span>](index.md)
