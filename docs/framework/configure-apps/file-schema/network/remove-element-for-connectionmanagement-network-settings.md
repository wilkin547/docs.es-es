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
ms.openlocfilehash: 46157482d7ceb42b352c68dc9b0eab4f7688bc5c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176180"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="a6a8d-102">Elemento \<remove> para connectionManagement (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="a6a8d-102">\<remove> Element for connectionManagement (Network Settings)</span></span>

<span data-ttu-id="a6a8d-103">Quita una dirección IP o un nombre DNS de la lista de administración de conexiones.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-103">Removes an IP address or DNS name from the connection management list.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="a6a8d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6a8d-104">Syntax</span></span>  
  
```xml  
<remove
  address="server name or IP address"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6a8d-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a6a8d-105">Attributes and Elements</span></span>  

 <span data-ttu-id="a6a8d-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6a8d-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="a6a8d-107">Attributes</span></span>  
  
|<span data-ttu-id="a6a8d-108">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="a6a8d-108">**Attribute**</span></span>|<span data-ttu-id="a6a8d-109">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a6a8d-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="a6a8d-110">Una dirección IP o un nombre DNS.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-110">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a6a8d-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a6a8d-111">Child Elements</span></span>  

 <span data-ttu-id="a6a8d-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a6a8d-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a6a8d-113">Parent Elements</span></span>  
  
|<span data-ttu-id="a6a8d-114">**Element**</span><span class="sxs-lookup"><span data-stu-id="a6a8d-114">**Element**</span></span>|<span data-ttu-id="a6a8d-115">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a6a8d-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a6a8d-116">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="a6a8d-116">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="a6a8d-117">Especifica el número máximo de conexiones a un host de red.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-117">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6a8d-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a6a8d-118">Remarks</span></span>  

 <span data-ttu-id="a6a8d-119">El `remove` elemento quita la entrada de la lista de administración de conexiones para el servidor especificado.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-119">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="a6a8d-120">El valor del `address` atributo debe ser una dirección IP o un nombre de host válidos.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-120">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a6a8d-121">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="a6a8d-121">Configuration Files</span></span>  

 <span data-ttu-id="a6a8d-122">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="a6a8d-122">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6a8d-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a6a8d-123">Example</span></span>  

 <span data-ttu-id="a6a8d-124">En el ejemplo siguiente se quitan las entradas de la lista de administración de conexiones del servidor `www.adventure-works.com` y, a continuación, se configura una aplicación para que use cuatro conexiones al servidor `www.contoso.com` y dos conexiones a todos los demás servidores.</span><span class="sxs-lookup"><span data-stu-id="a6a8d-124">The following example removes any connection management list entries for the server `www.adventure-works.com` and then configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a6a8d-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a6a8d-125">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="a6a8d-126">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="a6a8d-126">Network Settings Schema</span></span>](index.md)
