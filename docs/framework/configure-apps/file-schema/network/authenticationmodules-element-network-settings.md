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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154977"
---
# <a name="authenticationmodules-element-network-settings"></a><span data-ttu-id="c10a8-102">Elemento \<authenticationModules> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="c10a8-102">\<authenticationModules> Element (Network Settings)</span></span>
<span data-ttu-id="c10a8-103">Especifica los módulos que se usan para autenticar las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="c10a8-103">Specifies modules used to authenticate network requests.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<authenticationModules>**

## <a name="syntax"></a><span data-ttu-id="c10a8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c10a8-104">Syntax</span></span>  
  
```xml  
<authenticationModules>
</authenticationModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c10a8-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c10a8-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c10a8-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c10a8-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c10a8-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="c10a8-107">Attributes</span></span>  
 <span data-ttu-id="c10a8-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c10a8-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c10a8-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c10a8-109">Child Elements</span></span>  
  
|<span data-ttu-id="c10a8-110">**Element**</span><span class="sxs-lookup"><span data-stu-id="c10a8-110">**Element**</span></span>|<span data-ttu-id="c10a8-111">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c10a8-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c10a8-112">add</span><span class="sxs-lookup"><span data-stu-id="c10a8-112">add</span></span>](add-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="c10a8-113">Agrega un módulo de autenticación a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c10a8-113">Adds an authentication module to the application.</span></span>|  
|[<span data-ttu-id="c10a8-114">clear</span><span class="sxs-lookup"><span data-stu-id="c10a8-114">clear</span></span>](clear-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="c10a8-115">Borra todos los módulos de autenticación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c10a8-115">Clears all authentication modules from the application.</span></span>|  
|[<span data-ttu-id="c10a8-116">remove</span><span class="sxs-lookup"><span data-stu-id="c10a8-116">remove</span></span>](remove-element-for-authenticationmodules-network-settings.md)|<span data-ttu-id="c10a8-117">Quita un módulo de autenticación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c10a8-117">Removes an authentication module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c10a8-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c10a8-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c10a8-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="c10a8-119">**Element**</span></span>|<span data-ttu-id="c10a8-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c10a8-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c10a8-121">system.net</span><span class="sxs-lookup"><span data-stu-id="c10a8-121">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="c10a8-122">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="c10a8-122">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c10a8-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c10a8-123">Remarks</span></span>  
 <span data-ttu-id="c10a8-124">El `authenticationModule` elemento especifica los módulos de autenticación que llevan a cabo el proceso de autenticación con un servidor.</span><span class="sxs-lookup"><span data-stu-id="c10a8-124">The `authenticationModule` element specifies the authentication modules that conduct the authentication process with a server.</span></span> <span data-ttu-id="c10a8-125">Un módulo de autenticación debe implementar la <xref:System.Net.IAuthenticationModule> interfaz.</span><span class="sxs-lookup"><span data-stu-id="c10a8-125">An authentication module must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c10a8-126">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="c10a8-126">Configuration Files</span></span>  
 <span data-ttu-id="c10a8-127">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="c10a8-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c10a8-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c10a8-128">Example</span></span>  
 <span data-ttu-id="c10a8-129">En el ejemplo siguiente se habilita un módulo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="c10a8-129">The following example enables an authentication module.</span></span> <span data-ttu-id="c10a8-130">Debe reemplazar los valores de version y PublicKeyToken por los valores correctos para el módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="c10a8-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c10a8-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c10a8-131">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="c10a8-132">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="c10a8-132">Network Settings Schema</span></span>](index.md)
