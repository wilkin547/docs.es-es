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
ms.openlocfilehash: 05e4a1bc42dc39c7d2b56e30c98bdeefd31e4416
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149483"
---
# <a name="add-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="18264-102">Elemento \<add> para connectionManagement (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="18264-102">\<add> Element for connectionManagement (Network Settings)</span></span>

<span data-ttu-id="18264-103">Agrega una dirección IP o nombre DNS a la lista de administración de conexión.</span><span class="sxs-lookup"><span data-stu-id="18264-103">Adds an IP address or DNS name to the connection management list.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="18264-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="18264-104">Syntax</span></span>  
  
```xml  
<add
  address="address expression"
  maxconnection="integer"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18264-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="18264-105">Attributes and Elements</span></span>  

 <span data-ttu-id="18264-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="18264-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18264-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="18264-107">Attributes</span></span>  
  
|<span data-ttu-id="18264-108">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="18264-108">**Attribute**</span></span>|<span data-ttu-id="18264-109">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="18264-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="18264-110">Cadena que describe una dirección IP o nombre DNS.</span><span class="sxs-lookup"><span data-stu-id="18264-110">A string describing an IP address or DNS name.</span></span>|  
|`maxconnection`|<span data-ttu-id="18264-111">Número máximo de conexiones permitido en un servidor.</span><span class="sxs-lookup"><span data-stu-id="18264-111">The maximum number of connections allowed to a server.</span></span> <span data-ttu-id="18264-112">Si no se proporciona, el valor predeterminado es 2.</span><span class="sxs-lookup"><span data-stu-id="18264-112">If not supplied, the default is 2.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="18264-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="18264-113">Child Elements</span></span>  

 <span data-ttu-id="18264-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="18264-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="18264-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="18264-115">Parent Elements</span></span>  
  
|<span data-ttu-id="18264-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="18264-116">**Element**</span></span>|<span data-ttu-id="18264-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="18264-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="18264-118">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="18264-118">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="18264-119">Especifica el número máximo de conexiones a un host de red.</span><span class="sxs-lookup"><span data-stu-id="18264-119">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18264-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="18264-120">Remarks</span></span>  

 <span data-ttu-id="18264-121">El valor de la `address` atributo debe ser un asterisco para indicar todas las conexiones, o bien una cadena del formulario `<schema>://<idn_hostname>[:<port>]`.</span><span class="sxs-lookup"><span data-stu-id="18264-121">The value of the `address` attribute should be either an asterisk to indicate all connections, or a string of the form `<schema>://<idn_hostname>[:<port>]`.</span></span>  
  
 <span data-ttu-id="18264-122">Si el URI pasado a cualquier API de HTTP contiene Unicode, el nombre se convertirá internamente mediante <xref:System.Uri.DnsSafeHost%2A>, que puede devolver una cadena de punicode (comportamiento dependiente de la configuración actual de IDN).</span><span class="sxs-lookup"><span data-stu-id="18264-122">If the URI passed to any HTTP APIs contains Unicode, the name will be converted internally using <xref:System.Uri.DnsSafeHost%2A> which might return a punicode string (behavior dependent on the current IDN configuration).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="18264-123">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="18264-123">Configuration Files</span></span>  

 <span data-ttu-id="18264-124">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="18264-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="18264-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="18264-125">Example</span></span>  

 <span data-ttu-id="18264-126">En el ejemplo siguiente se configura una aplicación para que use cuatro conexiones al servidor `www.contoso.com` y dos conexiones a todos los demás servidores.</span><span class="sxs-lookup"><span data-stu-id="18264-126">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="18264-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="18264-127">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="18264-128">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="18264-128">Network Settings Schema</span></span>](index.md)
