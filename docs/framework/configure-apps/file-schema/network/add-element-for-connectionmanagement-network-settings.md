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
ms.openlocfilehash: 3742a040e8c16c38e495a0fd886c4c1f23780758
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698387"
---
# <a name="add-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="2a73a-102">\<add elemento > para connectionManagement (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="2a73a-102">\<add> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="2a73a-103">Agrega una dirección IP o nombre DNS a la lista de administración de conexión.</span><span class="sxs-lookup"><span data-stu-id="2a73a-103">Adds an IP address or DNS name to the connection management list.</span></span>  
  
[<span data-ttu-id="2a73a-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="2a73a-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="2a73a-105">&nbsp; @ no__t-1[ **@no__t -4System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="2a73a-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="2a73a-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<connectionManagement >** ](connectionmanagement-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="2a73a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)</span></span>  
<span data-ttu-id="2a73a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Agregar >**</span><span class="sxs-lookup"><span data-stu-id="2a73a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a73a-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a73a-108">Syntax</span></span>  
  
```xml  
<add   
  address="address expression"   
  maxconnection="integer"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a73a-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2a73a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2a73a-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2a73a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a73a-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="2a73a-111">Attributes</span></span>  
  
|<span data-ttu-id="2a73a-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="2a73a-112">**Attribute**</span></span>|<span data-ttu-id="2a73a-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2a73a-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="2a73a-114">Cadena que describe una dirección IP o nombre DNS.</span><span class="sxs-lookup"><span data-stu-id="2a73a-114">A string describing an IP address or DNS name.</span></span>|  
|`maxconnection`|<span data-ttu-id="2a73a-115">Número máximo de conexiones permitido en un servidor.</span><span class="sxs-lookup"><span data-stu-id="2a73a-115">The maximum number of connections allowed to a server.</span></span> <span data-ttu-id="2a73a-116">Si no se proporciona, el valor predeterminado es 2.</span><span class="sxs-lookup"><span data-stu-id="2a73a-116">If not supplied, the default is 2.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2a73a-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2a73a-117">Child Elements</span></span>  
 <span data-ttu-id="2a73a-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2a73a-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2a73a-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2a73a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="2a73a-120">**Element**</span><span class="sxs-lookup"><span data-stu-id="2a73a-120">**Element**</span></span>|<span data-ttu-id="2a73a-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2a73a-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2a73a-122">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="2a73a-122">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="2a73a-123">Especifica el número máximo de conexiones a un host de red.</span><span class="sxs-lookup"><span data-stu-id="2a73a-123">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a73a-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2a73a-124">Remarks</span></span>  
 <span data-ttu-id="2a73a-125">El valor de la `address` atributo debe ser un asterisco para indicar todas las conexiones, o bien una cadena del formulario `<schema>://<idn_hostname>[:<port>]`.</span><span class="sxs-lookup"><span data-stu-id="2a73a-125">The value of the `address` attribute should be either an asterisk to indicate all connections, or a string of the form `<schema>://<idn_hostname>[:<port>]`.</span></span>  
  
 <span data-ttu-id="2a73a-126">Si el URI pasado a cualquier API de HTTP contiene Unicode, el nombre se convertirá internamente mediante <xref:System.Uri.DnsSafeHost%2A>, que puede devolver una cadena de punicode (comportamiento dependiente de la configuración actual de IDN).</span><span class="sxs-lookup"><span data-stu-id="2a73a-126">If the URI passed to any HTTP APIs contains Unicode, the name will be converted internally using <xref:System.Uri.DnsSafeHost%2A> which might return a punicode string (behavior dependent on the current IDN configuration).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="2a73a-127">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="2a73a-127">Configuration Files</span></span>  
 <span data-ttu-id="2a73a-128">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="2a73a-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a73a-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2a73a-129">Example</span></span>  
 <span data-ttu-id="2a73a-130">En el ejemplo siguiente se configura una aplicación para que use cuatro conexiones al servidor `www.contoso.com` y dos conexiones a todos los demás servidores.</span><span class="sxs-lookup"><span data-stu-id="2a73a-130">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2a73a-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a73a-131">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="2a73a-132">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="2a73a-132">Network Settings Schema</span></span>](index.md)
