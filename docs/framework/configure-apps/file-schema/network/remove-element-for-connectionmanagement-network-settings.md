---
title: Elemento <remove> para connectionManagement (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- connectionManagement, remove element
- <remove> element, connectionManagement
- <connectionManagement>, remove element
- remove element, connectionManagement
ms.assetid: 94b81775-5a22-4975-8c47-8620c40c3f35
ms.openlocfilehash: 39ce85c3c15a2d4bdfce801a35e9ca088bd5091b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154743"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="1fc16-102">\<eliminar> Elemento para connectionManagement (Configuración de red)</span><span class="sxs-lookup"><span data-stu-id="1fc16-102">\<remove> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="1fc16-103">Quita una dirección IP o un nombre DNS de la lista de administración de conexiones.</span><span class="sxs-lookup"><span data-stu-id="1fc16-103">Removes an IP address or DNS name from the connection management list.</span></span>  

<span data-ttu-id="1fc16-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1fc16-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1fc16-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="1fc16-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="1fc16-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="1fc16-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)</span></span>\
<span data-ttu-id="1fc16-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<eliminar>**</span><span class="sxs-lookup"><span data-stu-id="1fc16-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="1fc16-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1fc16-108">Syntax</span></span>  
  
```xml  
<remove
  address="server name or IP address"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1fc16-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1fc16-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1fc16-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1fc16-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1fc16-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="1fc16-111">Attributes</span></span>  
  
|<span data-ttu-id="1fc16-112">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="1fc16-112">**Attribute**</span></span>|<span data-ttu-id="1fc16-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1fc16-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="1fc16-114">Una dirección IP o un nombre DNS.</span><span class="sxs-lookup"><span data-stu-id="1fc16-114">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1fc16-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1fc16-115">Child Elements</span></span>  
 <span data-ttu-id="1fc16-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1fc16-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1fc16-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1fc16-117">Parent Elements</span></span>  
  
|<span data-ttu-id="1fc16-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="1fc16-118">**Element**</span></span>|<span data-ttu-id="1fc16-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1fc16-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1fc16-120">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="1fc16-120">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="1fc16-121">Especifica el número máximo de conexiones a un host de red.</span><span class="sxs-lookup"><span data-stu-id="1fc16-121">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1fc16-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1fc16-122">Remarks</span></span>  
 <span data-ttu-id="1fc16-123">El `remove` elemento quita la entrada de lista de administración de conexiones para el servidor especificado.</span><span class="sxs-lookup"><span data-stu-id="1fc16-123">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="1fc16-124">El valor `address` del atributo debe ser una dirección IP o un nombre de host válidos.</span><span class="sxs-lookup"><span data-stu-id="1fc16-124">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="1fc16-125">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="1fc16-125">Configuration Files</span></span>  
 <span data-ttu-id="1fc16-126">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="1fc16-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1fc16-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1fc16-127">Example</span></span>  
 <span data-ttu-id="1fc16-128">En el ejemplo siguiente se quitan las `www.adventure-works.com` entradas de lista de administración de `www.contoso.com` conexiones para el servidor y, a continuación, se configura una aplicación para que use cuatro conexiones al servidor y dos conexiones a todos los demás servidores.</span><span class="sxs-lookup"><span data-stu-id="1fc16-128">The following example removes any connection management list entries for the server `www.adventure-works.com` and then configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1fc16-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1fc16-129">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="1fc16-130">Esquema de configuración de red</span><span class="sxs-lookup"><span data-stu-id="1fc16-130">Network Settings Schema</span></span>](index.md)
