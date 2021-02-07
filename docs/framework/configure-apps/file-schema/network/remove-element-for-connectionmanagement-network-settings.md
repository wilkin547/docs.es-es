---
description: 'Más información sobre: <remove> elemento para connectionManagement (configuración de red)'
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
ms.openlocfilehash: 98916846fb5de93ee93a7e25530e983cbd3719ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740254"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="fc4e3-103">Elemento \<remove> para connectionManagement (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="fc4e3-103">\<remove> Element for connectionManagement (Network Settings)</span></span>

<span data-ttu-id="fc4e3-104">Quita una dirección IP o un nombre DNS de la lista de administración de conexiones.</span><span class="sxs-lookup"><span data-stu-id="fc4e3-104">Removes an IP address or DNS name from the connection management list.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="fc4e3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc4e3-105">Syntax</span></span>  
  
```xml  
<remove
  address="server name or IP address"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc4e3-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fc4e3-106">Attributes and Elements</span></span>  

 <span data-ttu-id="fc4e3-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fc4e3-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc4e3-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="fc4e3-108">Attributes</span></span>  
  
|<span data-ttu-id="fc4e3-109">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="fc4e3-109">**Attribute**</span></span>|<span data-ttu-id="fc4e3-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="fc4e3-110">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="fc4e3-111">Una dirección IP o un nombre DNS.</span><span class="sxs-lookup"><span data-stu-id="fc4e3-111">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc4e3-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fc4e3-112">Child Elements</span></span>  

 <span data-ttu-id="fc4e3-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fc4e3-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fc4e3-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fc4e3-114">Parent Elements</span></span>  
  
|<span data-ttu-id="fc4e3-115">**Element**</span><span class="sxs-lookup"><span data-stu-id="fc4e3-115">**Element**</span></span>|<span data-ttu-id="fc4e3-116">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="fc4e3-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="fc4e3-117">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="fc4e3-117">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="fc4e3-118">Especifica el número máximo de conexiones a un host de red.</span><span class="sxs-lookup"><span data-stu-id="fc4e3-118">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc4e3-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fc4e3-119">Remarks</span></span>  

 <span data-ttu-id="fc4e3-120">El `remove` elemento quita la entrada de la lista de administración de conexiones para el servidor especificado.</span><span class="sxs-lookup"><span data-stu-id="fc4e3-120">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="fc4e3-121">El valor del `address` atributo debe ser una dirección IP o un nombre de host válidos.</span><span class="sxs-lookup"><span data-stu-id="fc4e3-121">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="fc4e3-122">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="fc4e3-122">Configuration Files</span></span>  

 <span data-ttu-id="fc4e3-123">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="fc4e3-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc4e3-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fc4e3-124">Example</span></span>  

 <span data-ttu-id="fc4e3-125">En el ejemplo siguiente se quitan las entradas de la lista de administración de conexiones del servidor `www.adventure-works.com` y, a continuación, se configura una aplicación para que use cuatro conexiones al servidor `www.contoso.com` y dos conexiones a todos los demás servidores.</span><span class="sxs-lookup"><span data-stu-id="fc4e3-125">The following example removes any connection management list entries for the server `www.adventure-works.com` and then configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fc4e3-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc4e3-126">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="fc4e3-127">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="fc4e3-127">Network Settings Schema</span></span>](index.md)
