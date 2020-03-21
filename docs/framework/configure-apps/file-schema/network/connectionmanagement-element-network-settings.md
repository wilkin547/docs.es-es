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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154899"
---
# <a name="connectionmanagement-element-network-settings"></a><span data-ttu-id="99949-102">\<Elemento connectionManagement> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="99949-102">\<connectionManagement> Element (Network Settings)</span></span>
<span data-ttu-id="99949-103">Especifica el número máximo de conexiones a un host de red.</span><span class="sxs-lookup"><span data-stu-id="99949-103">Specifies the maximum number of connections to a network host.</span></span>  

<span data-ttu-id="99949-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="99949-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="99949-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="99949-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="99949-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionManagement>**</span><span class="sxs-lookup"><span data-stu-id="99949-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionManagement>**</span></span>

## <a name="syntax"></a><span data-ttu-id="99949-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99949-107">Syntax</span></span>  
  
```xml  
<connectionManagement>
</connectionManagement>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99949-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="99949-108">Attributes and Elements</span></span>  
 <span data-ttu-id="99949-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="99949-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99949-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="99949-110">Attributes</span></span>  
 <span data-ttu-id="99949-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="99949-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="99949-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="99949-112">Child Elements</span></span>  
  
|<span data-ttu-id="99949-113">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="99949-113">**Element**</span></span>|<span data-ttu-id="99949-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="99949-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="99949-115">agregar</span><span class="sxs-lookup"><span data-stu-id="99949-115">add</span></span>](add-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="99949-116">Agrega una dirección IP o nombre DNS a la lista de administración de conexión.</span><span class="sxs-lookup"><span data-stu-id="99949-116">Adds an IP address or DNS name to the connection management list.</span></span>|  
|[<span data-ttu-id="99949-117">Claro</span><span class="sxs-lookup"><span data-stu-id="99949-117">clear</span></span>](clear-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="99949-118">Borra la lista de administración de conexiones.</span><span class="sxs-lookup"><span data-stu-id="99949-118">Clears the connection management list.</span></span>|  
|[<span data-ttu-id="99949-119">quitar</span><span class="sxs-lookup"><span data-stu-id="99949-119">remove</span></span>](remove-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="99949-120">Quita una dirección IP o un nombre DNS de la lista de administración de conexiones.</span><span class="sxs-lookup"><span data-stu-id="99949-120">Removes an IP address or DNS name from the connection management list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="99949-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="99949-121">Parent Elements</span></span>  
  
|<span data-ttu-id="99949-122">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="99949-122">**Element**</span></span>|<span data-ttu-id="99949-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="99949-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="99949-124">system.net</span><span class="sxs-lookup"><span data-stu-id="99949-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="99949-125">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="99949-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99949-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="99949-126">Remarks</span></span>  
 <span data-ttu-id="99949-127">El `connectionManagement` elemento define el número máximo de conexiones a un servidor o grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="99949-127">The `connectionManagement` element defines the maximum number of connections to a server or group of servers.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="99949-128">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="99949-128">Configuration Files</span></span>  
 <span data-ttu-id="99949-129">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="99949-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="99949-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="99949-130">Example</span></span>  
 <span data-ttu-id="99949-131">En el ejemplo siguiente se configura una `www.contoso.com` aplicación para utilizar cuatro conexiones al servidor y dos conexiones a todos los demás servidores.</span><span class="sxs-lookup"><span data-stu-id="99949-131">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="99949-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="99949-132">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="99949-133">Esquema de configuración de red</span><span class="sxs-lookup"><span data-stu-id="99949-133">Network Settings Schema</span></span>](index.md)
