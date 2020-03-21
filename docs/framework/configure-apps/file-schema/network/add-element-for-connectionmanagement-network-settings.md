---
title: Elemento <add> para connectionManagement (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/add
helpviewer_keywords:
- <add> element, connectionManagement
- <connectionManagement>, add element
- add element, connectionManagement
- connectionManagement, add element
ms.assetid: 856bf57d-1c63-46c7-a178-03d97b0a4149
ms.openlocfilehash: 093b68d31e03094bedefa96a2f2d53eb3d84edf0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155016"
---
# <a name="add-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="8acdf-102">\<Agregar> elemento para connectionManagement (Configuración de red)</span><span class="sxs-lookup"><span data-stu-id="8acdf-102">\<add> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="8acdf-103">Agrega una dirección IP o nombre DNS a la lista de administración de conexión.</span><span class="sxs-lookup"><span data-stu-id="8acdf-103">Adds an IP address or DNS name to the connection management list.</span></span>  

<span data-ttu-id="8acdf-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8acdf-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8acdf-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="8acdf-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="8acdf-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="8acdf-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)</span></span>\
<span data-ttu-id="8acdf-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<añadir>**</span><span class="sxs-lookup"><span data-stu-id="8acdf-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="8acdf-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8acdf-108">Syntax</span></span>  
  
```xml  
<add
  address="address expression"
  maxconnection="integer"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8acdf-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8acdf-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8acdf-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8acdf-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8acdf-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="8acdf-111">Attributes</span></span>  
  
|<span data-ttu-id="8acdf-112">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="8acdf-112">**Attribute**</span></span>|<span data-ttu-id="8acdf-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="8acdf-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="8acdf-114">Cadena que describe una dirección IP o nombre DNS.</span><span class="sxs-lookup"><span data-stu-id="8acdf-114">A string describing an IP address or DNS name.</span></span>|  
|`maxconnection`|<span data-ttu-id="8acdf-115">Número máximo de conexiones permitido en un servidor.</span><span class="sxs-lookup"><span data-stu-id="8acdf-115">The maximum number of connections allowed to a server.</span></span> <span data-ttu-id="8acdf-116">Si no se proporciona, el valor predeterminado es 2.</span><span class="sxs-lookup"><span data-stu-id="8acdf-116">If not supplied, the default is 2.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8acdf-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8acdf-117">Child Elements</span></span>  
 <span data-ttu-id="8acdf-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8acdf-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8acdf-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8acdf-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8acdf-120">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="8acdf-120">**Element**</span></span>|<span data-ttu-id="8acdf-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="8acdf-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8acdf-122">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="8acdf-122">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="8acdf-123">Especifica el número máximo de conexiones a un host de red.</span><span class="sxs-lookup"><span data-stu-id="8acdf-123">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8acdf-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8acdf-124">Remarks</span></span>  
 <span data-ttu-id="8acdf-125">El valor de la `address` atributo debe ser un asterisco para indicar todas las conexiones, o bien una cadena del formulario `<schema>://<idn_hostname>[:<port>]`.</span><span class="sxs-lookup"><span data-stu-id="8acdf-125">The value of the `address` attribute should be either an asterisk to indicate all connections, or a string of the form `<schema>://<idn_hostname>[:<port>]`.</span></span>  
  
 <span data-ttu-id="8acdf-126">Si el URI pasado a cualquier API de HTTP contiene Unicode, el nombre se convertirá internamente mediante <xref:System.Uri.DnsSafeHost%2A>, que puede devolver una cadena de punicode (comportamiento dependiente de la configuración actual de IDN).</span><span class="sxs-lookup"><span data-stu-id="8acdf-126">If the URI passed to any HTTP APIs contains Unicode, the name will be converted internally using <xref:System.Uri.DnsSafeHost%2A> which might return a punicode string (behavior dependent on the current IDN configuration).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8acdf-127">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="8acdf-127">Configuration Files</span></span>  
 <span data-ttu-id="8acdf-128">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="8acdf-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8acdf-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8acdf-129">Example</span></span>  
 <span data-ttu-id="8acdf-130">En el ejemplo siguiente se configura una `www.contoso.com` aplicación para utilizar cuatro conexiones al servidor y dos conexiones a todos los demás servidores.</span><span class="sxs-lookup"><span data-stu-id="8acdf-130">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8acdf-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8acdf-131">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="8acdf-132">Esquema de configuración de red</span><span class="sxs-lookup"><span data-stu-id="8acdf-132">Network Settings Schema</span></span>](index.md)
