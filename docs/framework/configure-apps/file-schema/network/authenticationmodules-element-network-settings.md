---
description: 'Más información acerca de: <authenticationModules> elemento (configuración de red)'
title: Elemento <authenticationModules> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#authenticationModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules
helpviewer_keywords:
- authenticationModules element
- <authenticationModules> element
ms.assetid: 10fcfaad-82ef-4692-871a-0aec9dfbe75e
ms.openlocfilehash: 2c2dc3c6a3d8fc064bb24c3d86a4441c269e43f0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698620"
---
# <a name="authenticationmodules-element-network-settings"></a><span data-ttu-id="19564-103">Elemento \<authenticationModules> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="19564-103">\<authenticationModules> Element (Network Settings)</span></span>

<span data-ttu-id="19564-104">Especifica los módulos que se usan para autenticar las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="19564-104">Specifies modules used to authenticate network requests.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<authenticationModules>**

## <a name="syntax"></a><span data-ttu-id="19564-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="19564-105">Syntax</span></span>  
  
```xml  
<authenticationModules>
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19564-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="19564-106">Attributes and Elements</span></span>  

 <span data-ttu-id="19564-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="19564-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19564-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="19564-108">Attributes</span></span>  

 <span data-ttu-id="19564-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="19564-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="19564-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="19564-110">Child Elements</span></span>  
  
|<span data-ttu-id="19564-111">**Element**</span><span class="sxs-lookup"><span data-stu-id="19564-111">**Element**</span></span>|<span data-ttu-id="19564-112">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="19564-112">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="19564-113">add</span><span class="sxs-lookup"><span data-stu-id="19564-113">add</span></span>](add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="19564-114">Agrega un módulo de autenticación a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="19564-114">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="19564-115">clear</span><span class="sxs-lookup"><span data-stu-id="19564-115">clear</span></span>](clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="19564-116">Borra todos los módulos de autenticación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="19564-116">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="19564-117">remove</span><span class="sxs-lookup"><span data-stu-id="19564-117">remove</span></span>](remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="19564-118">Quita un módulo de autenticación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="19564-118">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="19564-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="19564-119">Parent Elements</span></span>  
  
|<span data-ttu-id="19564-120">**Element**</span><span class="sxs-lookup"><span data-stu-id="19564-120">**Element**</span></span>|<span data-ttu-id="19564-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="19564-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="19564-122">system.net</span><span class="sxs-lookup"><span data-stu-id="19564-122">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="19564-123">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="19564-123">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19564-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="19564-124">Remarks</span></span>  

 <span data-ttu-id="19564-125">El `authenticationModule` elemento especifica los módulos de autenticación que llevan a cabo el proceso de autenticación con un servidor.</span><span class="sxs-lookup"><span data-stu-id="19564-125">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="19564-126">Un módulo de autenticación debe implementar la <xref:System.Net.IAuthenticationModule> interfaz.</span><span class="sxs-lookup"><span data-stu-id="19564-126">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="19564-127">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="19564-127">Configuration Files</span></span>  

 <span data-ttu-id="19564-128">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="19564-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="19564-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="19564-129">Example</span></span>  

 <span data-ttu-id="19564-130">En el ejemplo siguiente se habilita un módulo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="19564-130">The following example enables an authentication module.</span></span> <span data-ttu-id="19564-131">Debe reemplazar los valores de version y PublicKeyToken por los valores correctos para el módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="19564-131">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="19564-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="19564-132">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="19564-133">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="19564-133">Network Settings Schema</span></span>](index.md)
