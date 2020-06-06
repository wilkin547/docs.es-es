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
ms.openlocfilehash: a76df48a9de084e1121a5e96b22edf7aa3acba23
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088488"
---
# <a name="clear-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="4041b-102">Elemento \<clear> para connectionManagement (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="4041b-102">\<clear> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="4041b-103">Borra la lista de administración de conexiones.</span><span class="sxs-lookup"><span data-stu-id="4041b-103">Clears the connection management list.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="4041b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4041b-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4041b-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4041b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4041b-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4041b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4041b-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="4041b-107">Attributes</span></span>  
 <span data-ttu-id="4041b-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4041b-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4041b-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4041b-109">Child Elements</span></span>  
 <span data-ttu-id="4041b-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4041b-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4041b-111">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4041b-111">Parent Elements</span></span>  
  
|<span data-ttu-id="4041b-112">**Element**</span><span class="sxs-lookup"><span data-stu-id="4041b-112">**Element**</span></span>|<span data-ttu-id="4041b-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="4041b-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4041b-114">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="4041b-114">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="4041b-115">Especifica el número máximo de conexiones a un host de red.</span><span class="sxs-lookup"><span data-stu-id="4041b-115">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4041b-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4041b-116">Remarks</span></span>  
 <span data-ttu-id="4041b-117">El `clear` elemento borra todas las entradas de la lista de administración de conexiones.</span><span class="sxs-lookup"><span data-stu-id="4041b-117">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4041b-118">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="4041b-118">Configuration Files</span></span>  
 <span data-ttu-id="4041b-119">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="4041b-119">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4041b-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4041b-120">Example</span></span>  
 <span data-ttu-id="4041b-121">En el siguiente ejemplo se borra la lista de administración de conexiones y, después, se agregan nuevas entradas de administración de conexiones para el servidor `www.contoso.com` y todos los demás hosts de red.</span><span class="sxs-lookup"><span data-stu-id="4041b-121">The following example clears the connection management list and then adds new connection management entries for the server `www.contoso.com` and all other network hosts.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4041b-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4041b-122">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="4041b-123">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="4041b-123">Network Settings Schema</span></span>](index.md)
