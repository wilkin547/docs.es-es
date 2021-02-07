---
description: 'Más información sobre: <clear> elemento para connectionManagement (configuración de red)'
title: Elemento <clear> para connectionManagement (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, connectionManagement
- connectionManagement, clear element
- clear element, connectionManagement
- <connectionManagement>, clear element
ms.assetid: fb259282-84c4-4dc4-a226-78d904a6edc3
ms.openlocfilehash: e6e756e1065e48e79d59e02858963ded70d30f7e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698594"
---
# <a name="clear-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="06686-103">Elemento \<clear> para connectionManagement (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="06686-103">\<clear> Element for connectionManagement (Network Settings)</span></span>

<span data-ttu-id="06686-104">Borra la lista de administración de conexiones.</span><span class="sxs-lookup"><span data-stu-id="06686-104">Clears the connection management list.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="06686-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06686-105">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06686-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="06686-106">Attributes and Elements</span></span>  

 <span data-ttu-id="06686-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="06686-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06686-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="06686-108">Attributes</span></span>  

 <span data-ttu-id="06686-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="06686-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="06686-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="06686-110">Child Elements</span></span>  

 <span data-ttu-id="06686-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="06686-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="06686-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="06686-112">Parent Elements</span></span>  
  
|<span data-ttu-id="06686-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="06686-113">**Element**</span></span>|<span data-ttu-id="06686-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="06686-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="06686-115">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="06686-115">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="06686-116">Especifica el número máximo de conexiones a un host de red.</span><span class="sxs-lookup"><span data-stu-id="06686-116">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06686-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="06686-117">Remarks</span></span>  

 <span data-ttu-id="06686-118">El `clear` elemento borra todas las entradas de la lista de administración de conexiones.</span><span class="sxs-lookup"><span data-stu-id="06686-118">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="06686-119">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="06686-119">Configuration Files</span></span>  

 <span data-ttu-id="06686-120">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="06686-120">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="06686-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="06686-121">Example</span></span>  

 <span data-ttu-id="06686-122">En el siguiente ejemplo se borra la lista de administración de conexiones y, después, se agregan nuevas entradas de administración de conexiones para el servidor `www.contoso.com` y todos los demás hosts de red.</span><span class="sxs-lookup"><span data-stu-id="06686-122">The following example clears the connection management list and then adds new connection management entries for the server `www.contoso.com` and all other network hosts.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <clear/>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="06686-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="06686-123">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="06686-124">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="06686-124">Network Settings Schema</span></span>](index.md)
