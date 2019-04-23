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
ms.openlocfilehash: d9c584fb2faa971e7ce1ca287a94c8c6129820fd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59158865"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="56726-102">\<Quitar > elemento para connectionManagement (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="56726-102">\<remove> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="56726-103">Quita una dirección IP o nombre DNS de la lista de administración de conexiones.</span><span class="sxs-lookup"><span data-stu-id="56726-103">Removes an IP address or DNS name from the connection management list.</span></span>  
  
 <span data-ttu-id="56726-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="56726-104">\<configuration></span></span>  
<span data-ttu-id="56726-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="56726-105">\<system.net></span></span>  
<span data-ttu-id="56726-106">\<connectionManagement></span><span class="sxs-lookup"><span data-stu-id="56726-106">\<connectionManagement></span></span>  
<span data-ttu-id="56726-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="56726-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56726-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56726-108">Syntax</span></span>  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56726-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="56726-109">Attributes and Elements</span></span>  
 <span data-ttu-id="56726-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="56726-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56726-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="56726-111">Attributes</span></span>  
  
|<span data-ttu-id="56726-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="56726-112">**Attribute**</span></span>|<span data-ttu-id="56726-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="56726-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="56726-114">Una dirección IP o nombre DNS.</span><span class="sxs-lookup"><span data-stu-id="56726-114">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56726-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="56726-115">Child Elements</span></span>  
 <span data-ttu-id="56726-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="56726-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="56726-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="56726-117">Parent Elements</span></span>  
  
|<span data-ttu-id="56726-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="56726-118">**Element**</span></span>|<span data-ttu-id="56726-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="56726-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="56726-120">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="56726-120">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="56726-121">Especifica el número máximo de conexiones a un host de red.</span><span class="sxs-lookup"><span data-stu-id="56726-121">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56726-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="56726-122">Remarks</span></span>  
 <span data-ttu-id="56726-123">El `remove` elemento quita la entrada de lista de administración de conexión para el servidor especificado.</span><span class="sxs-lookup"><span data-stu-id="56726-123">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="56726-124">El valor de la `address` atributo debe ser un nombre de host o dirección IP válido.</span><span class="sxs-lookup"><span data-stu-id="56726-124">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="56726-125">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="56726-125">Configuration Files</span></span>  
 <span data-ttu-id="56726-126">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="56726-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="56726-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="56726-127">Example</span></span>  
 <span data-ttu-id="56726-128">En el ejemplo siguiente se quita cualquier entradas de lista de administración de conexión para el servidor `www.adventure-works.com` y, a continuación, configura una aplicación para usar cuatro conexiones al servidor `www.contoso.com` y dos conexiones con todos los demás servidores.</span><span class="sxs-lookup"><span data-stu-id="56726-128">The following example removes any connection management list entries for the server `www.adventure-works.com` and then configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="56726-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="56726-129">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="56726-130">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="56726-130">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
