---
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
ms.openlocfilehash: 17b380b12977423669fd413132d69a3082daca41
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698358"
---
# <a name="clear-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="73c1a-102">\<clear elemento > para connectionManagement (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="73c1a-102">\<clear> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="73c1a-103">Borra la lista de administración de conexiones.</span><span class="sxs-lookup"><span data-stu-id="73c1a-103">Clears the connection management list.</span></span>  
  
[<span data-ttu-id="73c1a-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="73c1a-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="73c1a-105">&nbsp; @ no__t-1[ **@no__t -4System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="73c1a-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="73c1a-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<connectionManagement >** ](connectionmanagement-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="73c1a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)</span></span>  
<span data-ttu-id="73c1a-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="73c1a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73c1a-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73c1a-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73c1a-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="73c1a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="73c1a-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="73c1a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73c1a-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="73c1a-111">Attributes</span></span>  
 <span data-ttu-id="73c1a-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="73c1a-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="73c1a-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="73c1a-113">Child Elements</span></span>  
 <span data-ttu-id="73c1a-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="73c1a-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="73c1a-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="73c1a-115">Parent Elements</span></span>  
  
|<span data-ttu-id="73c1a-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="73c1a-116">**Element**</span></span>|<span data-ttu-id="73c1a-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="73c1a-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="73c1a-118">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="73c1a-118">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="73c1a-119">Especifica el número máximo de conexiones a un host de red.</span><span class="sxs-lookup"><span data-stu-id="73c1a-119">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73c1a-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="73c1a-120">Remarks</span></span>  
 <span data-ttu-id="73c1a-121">El elemento `clear` borra todas las entradas de la lista de administración de conexiones.</span><span class="sxs-lookup"><span data-stu-id="73c1a-121">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="73c1a-122">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="73c1a-122">Configuration Files</span></span>  
 <span data-ttu-id="73c1a-123">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="73c1a-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="73c1a-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="73c1a-124">Example</span></span>  
 <span data-ttu-id="73c1a-125">En el siguiente ejemplo se borra la lista de administración de conexiones y, después, se agregan nuevas entradas de administración de conexiones para el servidor `www.contoso.com` y todos los demás hosts de red.</span><span class="sxs-lookup"><span data-stu-id="73c1a-125">The following example clears the connection management list and then adds new connection management entries for the server `www.contoso.com` and all other network hosts.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="73c1a-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="73c1a-126">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="73c1a-127">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="73c1a-127">Network Settings Schema</span></span>](index.md)
