---
title: '&lt;authenticationModules&gt; Element (Network Settings)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#authenticationModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules
helpviewer_keywords:
- authenticationModules element
- <authenticationModules> element
ms.assetid: 10fcfaad-82ef-4692-871a-0aec9dfbe75e
caps.latest.revision: "15"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: fe2e1757a3e2da5c2aa6084c0eb21164de3ece0e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltauthenticationmodulesgt-element-network-settings"></a><span data-ttu-id="7c347-102">&lt;authenticationModules&gt; Element (Network Settings)</span><span class="sxs-lookup"><span data-stu-id="7c347-102">&lt;authenticationModules&gt; Element (Network Settings)</span></span>
<span data-ttu-id="7c347-103">Especifica los módulos utilizados para autenticar las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="7c347-103">Specifies modules used to authenticate network requests.</span></span>  
  
 <span data-ttu-id="7c347-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7c347-104">\<configuration></span></span>  
<span data-ttu-id="7c347-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="7c347-105">\<system.net></span></span>  
<span data-ttu-id="7c347-106">\<authenticationModules ></span><span class="sxs-lookup"><span data-stu-id="7c347-106">\<authenticationModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c347-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7c347-107">Syntax</span></span>  
  
```xml  
<authenticationModules>   
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7c347-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7c347-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7c347-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7c347-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7c347-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="7c347-110">Attributes</span></span>  
 <span data-ttu-id="7c347-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7c347-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7c347-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7c347-112">Child Elements</span></span>  
  
|<span data-ttu-id="7c347-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="7c347-113">**Element**</span></span>|<span data-ttu-id="7c347-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7c347-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="7c347-115">add</span><span class="sxs-lookup"><span data-stu-id="7c347-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="7c347-116">Agrega un módulo de autenticación a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7c347-116">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="7c347-117">clear</span><span class="sxs-lookup"><span data-stu-id="7c347-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="7c347-118">Borra todos los módulos de autenticación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7c347-118">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="7c347-119">remove</span><span class="sxs-lookup"><span data-stu-id="7c347-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="7c347-120">Quita un módulo de autenticación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7c347-120">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7c347-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7c347-121">Parent Elements</span></span>  
  
|<span data-ttu-id="7c347-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="7c347-122">**Element**</span></span>|<span data-ttu-id="7c347-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7c347-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="7c347-124">System.NET</span><span class="sxs-lookup"><span data-stu-id="7c347-124">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="7c347-125">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="7c347-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c347-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7c347-126">Remarks</span></span>  
 <span data-ttu-id="7c347-127">El `authenticationModule` elemento especifica los módulos de autenticación que lleven a cabo el proceso de autenticación con un servidor.</span><span class="sxs-lookup"><span data-stu-id="7c347-127">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="7c347-128">Un módulo de autenticación debe implementar la <xref:System.Net.IAuthenticationModule> interfaz.</span><span class="sxs-lookup"><span data-stu-id="7c347-128">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="7c347-129">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="7c347-129">Configuration Files</span></span>  
 <span data-ttu-id="7c347-130">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="7c347-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c347-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7c347-131">Example</span></span>  
 <span data-ttu-id="7c347-132">En el ejemplo siguiente se habilita un módulo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="7c347-132">The following example enables an authentication module.</span></span> <span data-ttu-id="7c347-133">Debe reemplazar los valores de Version y PublicKeyToken con los valores correctos para el módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="7c347-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7c347-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c347-134">See Also</span></span>  
 <xref:System.Net.IAuthenticationModule>  
 <xref:System.Net.AuthenticationManager>  
 [<span data-ttu-id="7c347-135">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="7c347-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
