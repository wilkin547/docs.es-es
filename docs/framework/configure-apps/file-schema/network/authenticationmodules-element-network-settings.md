---
title: Elemento <authenticationModules> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#authenticationModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules
helpviewer_keywords:
- authenticationModules element
- <authenticationModules> element
ms.assetid: 10fcfaad-82ef-4692-871a-0aec9dfbe75e
ms.openlocfilehash: b502cc4a0958f074018d4b0ce6b3fb118b811c2f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154977"
---
# <a name="authenticationmodules-element-network-settings"></a><span data-ttu-id="c179b-102">\<Elemento authenticationModules> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="c179b-102">\<authenticationModules> Element (Network Settings)</span></span>
<span data-ttu-id="c179b-103">Especifica los módulos utilizados para autenticar las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="c179b-103">Specifies modules used to authenticate network requests.</span></span>  

<span data-ttu-id="c179b-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c179b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c179b-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c179b-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="c179b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<authenticationModules>**</span><span class="sxs-lookup"><span data-stu-id="c179b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<authenticationModules>**</span></span>

## <a name="syntax"></a><span data-ttu-id="c179b-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c179b-107">Syntax</span></span>  
  
```xml  
<authenticationModules>
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c179b-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c179b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c179b-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c179b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c179b-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="c179b-110">Attributes</span></span>  
 <span data-ttu-id="c179b-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c179b-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c179b-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c179b-112">Child Elements</span></span>  
  
|<span data-ttu-id="c179b-113">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="c179b-113">**Element**</span></span>|<span data-ttu-id="c179b-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c179b-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c179b-115">agregar</span><span class="sxs-lookup"><span data-stu-id="c179b-115">add</span></span>](add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="c179b-116">Agrega un módulo de autenticación a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c179b-116">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="c179b-117">Claro</span><span class="sxs-lookup"><span data-stu-id="c179b-117">clear</span></span>](clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="c179b-118">Borra todos los módulos de autenticación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c179b-118">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="c179b-119">quitar</span><span class="sxs-lookup"><span data-stu-id="c179b-119">remove</span></span>](remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="c179b-120">Quita un módulo de autenticación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c179b-120">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c179b-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c179b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c179b-122">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="c179b-122">**Element**</span></span>|<span data-ttu-id="c179b-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c179b-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c179b-124">system.net</span><span class="sxs-lookup"><span data-stu-id="c179b-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="c179b-125">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="c179b-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c179b-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c179b-126">Remarks</span></span>  
 <span data-ttu-id="c179b-127">El `authenticationModule` elemento especifica los módulos de autenticación que llevan a cabo el proceso de autenticación con un servidor.</span><span class="sxs-lookup"><span data-stu-id="c179b-127">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="c179b-128">Un módulo de <xref:System.Net.IAuthenticationModule> autenticación debe implementar la interfaz.</span><span class="sxs-lookup"><span data-stu-id="c179b-128">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c179b-129">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="c179b-129">Configuration Files</span></span>  
 <span data-ttu-id="c179b-130">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="c179b-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c179b-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c179b-131">Example</span></span>  
 <span data-ttu-id="c179b-132">En el ejemplo siguiente se habilita un módulo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="c179b-132">The following example enables an authentication module.</span></span> <span data-ttu-id="c179b-133">Debe reemplazar los valores de Version y PublicKeyToken por los valores correctos para el módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="c179b-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c179b-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c179b-134">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="c179b-135">Esquema de configuración de red</span><span class="sxs-lookup"><span data-stu-id="c179b-135">Network Settings Schema</span></span>](index.md)
