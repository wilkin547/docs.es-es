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
ms.openlocfilehash: cbafd29be6855cbb95d17388791ba152230295cc
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697842"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="aea44-102">\<remove elemento > para connectionManagement (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="aea44-102">\<remove> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="aea44-103">Quita una dirección IP o un nombre DNS de la lista de administración de conexiones.</span><span class="sxs-lookup"><span data-stu-id="aea44-103">Removes an IP address or DNS name from the connection management list.</span></span>  
  
[<span data-ttu-id="aea44-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="aea44-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="aea44-105">&nbsp; @ no__t-1[ **@no__t -4System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="aea44-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="aea44-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<connectionManagement >** ](connectionmanagement-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="aea44-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)</span></span>  
<span data-ttu-id="aea44-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<remove >**</span><span class="sxs-lookup"><span data-stu-id="aea44-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aea44-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aea44-108">Syntax</span></span>  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aea44-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="aea44-109">Attributes and Elements</span></span>  
 <span data-ttu-id="aea44-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="aea44-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aea44-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="aea44-111">Attributes</span></span>  
  
|<span data-ttu-id="aea44-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="aea44-112">**Attribute**</span></span>|<span data-ttu-id="aea44-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="aea44-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="aea44-114">Una dirección IP o un nombre DNS.</span><span class="sxs-lookup"><span data-stu-id="aea44-114">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aea44-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="aea44-115">Child Elements</span></span>  
 <span data-ttu-id="aea44-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="aea44-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aea44-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="aea44-117">Parent Elements</span></span>  
  
|<span data-ttu-id="aea44-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="aea44-118">**Element**</span></span>|<span data-ttu-id="aea44-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="aea44-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="aea44-120">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="aea44-120">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="aea44-121">Especifica el número máximo de conexiones a un host de red.</span><span class="sxs-lookup"><span data-stu-id="aea44-121">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aea44-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aea44-122">Remarks</span></span>  
 <span data-ttu-id="aea44-123">El elemento `remove` quita la entrada de la lista de administración de conexiones para el servidor especificado.</span><span class="sxs-lookup"><span data-stu-id="aea44-123">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="aea44-124">El valor del atributo `address` debe ser una dirección IP o un nombre de host válidos.</span><span class="sxs-lookup"><span data-stu-id="aea44-124">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="aea44-125">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="aea44-125">Configuration Files</span></span>  
 <span data-ttu-id="aea44-126">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="aea44-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="aea44-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aea44-127">Example</span></span>  
 <span data-ttu-id="aea44-128">En el ejemplo siguiente se quitan las entradas de la lista de administración de conexiones del servidor `www.adventure-works.com` y, a continuación, se configura una aplicación para que use cuatro conexiones al servidor `www.contoso.com` y dos conexiones a todos los demás servidores.</span><span class="sxs-lookup"><span data-stu-id="aea44-128">The following example removes any connection management list entries for the server `www.adventure-works.com` and then configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="aea44-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="aea44-129">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="aea44-130">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="aea44-130">Network Settings Schema</span></span>](index.md)
