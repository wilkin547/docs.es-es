---
title: Elemento <clear> para authenticationModules (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, authenticationModules
- <authenticationModules>, clear element
- <clear> element, authenticationModules
- authenticationModules, clear element
ms.assetid: dc522c45-4a80-4831-8955-f7b68a47edfd
ms.openlocfilehash: 6ac2287ba9b17727835d43a3e3b8876f210fb5c7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167332"
---
# <a name="clear-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="1b69a-102">Elemento \<clear> para authenticationModules (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="1b69a-102">\<clear> Element for authenticationModules (Network Settings)</span></span>

<span data-ttu-id="1b69a-103">Borra todos los módulos de autenticación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1b69a-103">Clears all authentication modules from the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="1b69a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1b69a-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b69a-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1b69a-105">Attributes and Elements</span></span>  

 <span data-ttu-id="1b69a-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1b69a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b69a-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="1b69a-107">Attributes</span></span>  

 <span data-ttu-id="1b69a-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1b69a-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1b69a-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1b69a-109">Child Elements</span></span>  

 <span data-ttu-id="1b69a-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1b69a-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1b69a-111">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1b69a-111">Parent Elements</span></span>  
  
|<span data-ttu-id="1b69a-112">**Element**</span><span class="sxs-lookup"><span data-stu-id="1b69a-112">**Element**</span></span>|<span data-ttu-id="1b69a-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1b69a-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1b69a-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="1b69a-114">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="1b69a-115">Especifica los módulos que se usan para autenticar las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="1b69a-115">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b69a-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1b69a-116">Remarks</span></span>  

 <span data-ttu-id="1b69a-117">El `clear` elemento quita todos los módulos de autenticación que se definieron anteriormente en el archivo de configuración o en un nivel superior en la jerarquía de configuración.</span><span class="sxs-lookup"><span data-stu-id="1b69a-117">The `clear` element removes all authentication modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="1b69a-118">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="1b69a-118">Configuration Files</span></span>  

 <span data-ttu-id="1b69a-119">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="1b69a-119">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b69a-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1b69a-120">Example</span></span>  

 <span data-ttu-id="1b69a-121">En el ejemplo siguiente se quitan todos los módulos de autenticación configurados.</span><span class="sxs-lookup"><span data-stu-id="1b69a-121">The following example removes all configured authentication modules.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <clear/>  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1b69a-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1b69a-122">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="1b69a-123">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="1b69a-123">Network Settings Schema</span></span>](index.md)
