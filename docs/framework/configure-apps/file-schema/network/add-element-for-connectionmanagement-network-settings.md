---
description: 'Más información sobre: <add> elemento para connectionManagement (configuración de red)'
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
ms.openlocfilehash: 646d9fcfb73cfd8f4f533672c1a92883274f6e39
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729945"
---
# <a name="add-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="adc85-103">Elemento \<add> para connectionManagement (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="adc85-103">\<add> Element for connectionManagement (Network Settings)</span></span>

<span data-ttu-id="adc85-104">Agrega una dirección IP o nombre DNS a la lista de administración de conexión.</span><span class="sxs-lookup"><span data-stu-id="adc85-104">Adds an IP address or DNS name to the connection management list.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="adc85-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="adc85-105">Syntax</span></span>  
  
```xml  
<add
  address="address expression"
  maxconnection="integer"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="adc85-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="adc85-106">Attributes and Elements</span></span>  

 <span data-ttu-id="adc85-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="adc85-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="adc85-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="adc85-108">Attributes</span></span>  
  
|<span data-ttu-id="adc85-109">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="adc85-109">**Attribute**</span></span>|<span data-ttu-id="adc85-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="adc85-110">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="adc85-111">Cadena que describe una dirección IP o nombre DNS.</span><span class="sxs-lookup"><span data-stu-id="adc85-111">A string describing an IP address or DNS name.</span></span>|  
|`maxconnection`|<span data-ttu-id="adc85-112">Número máximo de conexiones permitido en un servidor.</span><span class="sxs-lookup"><span data-stu-id="adc85-112">The maximum number of connections allowed to a server.</span></span> <span data-ttu-id="adc85-113">Si no se proporciona, el valor predeterminado es 2.</span><span class="sxs-lookup"><span data-stu-id="adc85-113">If not supplied, the default is 2.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="adc85-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="adc85-114">Child Elements</span></span>  

 <span data-ttu-id="adc85-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="adc85-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="adc85-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="adc85-116">Parent Elements</span></span>  
  
|<span data-ttu-id="adc85-117">**Element**</span><span class="sxs-lookup"><span data-stu-id="adc85-117">**Element**</span></span>|<span data-ttu-id="adc85-118">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="adc85-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="adc85-119">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="adc85-119">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="adc85-120">Especifica el número máximo de conexiones a un host de red.</span><span class="sxs-lookup"><span data-stu-id="adc85-120">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="adc85-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="adc85-121">Remarks</span></span>  

 <span data-ttu-id="adc85-122">El valor de la `address` atributo debe ser un asterisco para indicar todas las conexiones, o bien una cadena del formulario `<schema>://<idn_hostname>[:<port>]`.</span><span class="sxs-lookup"><span data-stu-id="adc85-122">The value of the `address` attribute should be either an asterisk to indicate all connections, or a string of the form `<schema>://<idn_hostname>[:<port>]`.</span></span>  
  
 <span data-ttu-id="adc85-123">Si el URI pasado a cualquier API de HTTP contiene Unicode, el nombre se convertirá internamente mediante <xref:System.Uri.DnsSafeHost%2A>, que puede devolver una cadena de punicode (comportamiento dependiente de la configuración actual de IDN).</span><span class="sxs-lookup"><span data-stu-id="adc85-123">If the URI passed to any HTTP APIs contains Unicode, the name will be converted internally using <xref:System.Uri.DnsSafeHost%2A> which might return a punicode string (behavior dependent on the current IDN configuration).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="adc85-124">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="adc85-124">Configuration Files</span></span>  

 <span data-ttu-id="adc85-125">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="adc85-125">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="adc85-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="adc85-126">Example</span></span>  

 <span data-ttu-id="adc85-127">En el ejemplo siguiente se configura una aplicación para que use cuatro conexiones al servidor `www.contoso.com` y dos conexiones a todos los demás servidores.</span><span class="sxs-lookup"><span data-stu-id="adc85-127">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="adc85-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="adc85-128">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="adc85-129">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="adc85-129">Network Settings Schema</span></span>](index.md)
