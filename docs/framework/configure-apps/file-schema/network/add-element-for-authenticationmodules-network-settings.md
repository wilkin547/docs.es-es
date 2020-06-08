---
title: Elemento <add> para authenticationModules (configuración de red)
description: El <add> elemento de configuración de red para connectionManagement agrega una dirección IP o un nombre DNS a la lista de administración de conexiones en el .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/add
helpviewer_keywords:
- authenticationModules, add element
- add element, authenticationModules
- <authenticationModules>, add element
- <add> element, authenticationModules
ms.assetid: 333c5fb0-a2ab-4db8-8531-a7fe37bb9b5b
ms.openlocfilehash: 1a6d0f79f076a69cec33ac14f0e0f33f7c3c6577
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504646"
---
# <a name="add-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="46233-103">Elemento \<add> para authenticationModules (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="46233-103">\<add> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="46233-104">Agrega un módulo de autenticación a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="46233-104">Adds an authentication module to the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="46233-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="46233-105">Syntax</span></span>  
  
```xml  
<add
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46233-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="46233-106">Attributes and Elements</span></span>  
 <span data-ttu-id="46233-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="46233-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46233-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="46233-108">Attributes</span></span>  
  
|<span data-ttu-id="46233-109">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="46233-109">**Attribute**</span></span>|<span data-ttu-id="46233-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="46233-110">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="46233-111">El nombre de tipo completo (indicado por la <xref:System.Type.FullName%2A> propiedad) y el nombre de ensamblado (indicado por la <xref:System.Reflection.Assembly.FullName%2A> propiedad), separados por una coma.</span><span class="sxs-lookup"><span data-stu-id="46233-111">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="46233-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="46233-112">Child Elements</span></span>  
 <span data-ttu-id="46233-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="46233-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="46233-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="46233-114">Parent Elements</span></span>  
  
|<span data-ttu-id="46233-115">**Element**</span><span class="sxs-lookup"><span data-stu-id="46233-115">**Element**</span></span>|<span data-ttu-id="46233-116">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="46233-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="46233-117">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="46233-117">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="46233-118">Especifica los módulos que se usan para autenticar las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="46233-118">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46233-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="46233-119">Remarks</span></span>  
 <span data-ttu-id="46233-120">El `add` elemento agrega un módulo de autenticación al final de la lista de módulos de autenticación registrados.</span><span class="sxs-lookup"><span data-stu-id="46233-120">The `add` element adds an authentication module to the end of the list of registered authentication modules.</span></span> <span data-ttu-id="46233-121">Los módulos de autenticación se llaman en el orden en que se agregaron a la lista.</span><span class="sxs-lookup"><span data-stu-id="46233-121">Authentication modules are called in the order in which they were added to the list.</span></span>  
  
 <span data-ttu-id="46233-122">El valor del `type` atributo debe ser un nombre de tipo válido y el nombre de ensamblado correspondiente, separados por una coma.</span><span class="sxs-lookup"><span data-stu-id="46233-122">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="46233-123">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="46233-123">Configuration Files</span></span>  
 <span data-ttu-id="46233-124">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="46233-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="46233-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="46233-125">Example</span></span>  
 <span data-ttu-id="46233-126">En el ejemplo siguiente se habilitan los módulos de autenticación predeterminados.</span><span class="sxs-lookup"><span data-stu-id="46233-126">The following example enables the default authentication modules.</span></span> <span data-ttu-id="46233-127">Debe reemplazar los valores de version y PublicKeyToken por los valores correctos para el módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="46233-127">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
        <authenticationModules>  
            <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NegotiateClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.KerberosClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NtlmClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.BasicClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
        </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="46233-128">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="46233-128">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="46233-129">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="46233-129">Network Settings Schema</span></span>](index.md)
