---
title: Elemento <add> para authenticationModules (configuración de red)
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
ms.openlocfilehash: a68434aaa118db60a502c2bcc0bb188b83b0f463
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698432"
---
# <a name="add-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="58ad1-102">\<add > elemento para authenticationModules (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="58ad1-102">\<add> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="58ad1-103">Agrega un módulo de autenticación a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="58ad1-103">Adds an authentication module to the application.</span></span>  
  
[<span data-ttu-id="58ad1-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="58ad1-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="58ad1-105">&nbsp; @ no__t-1[ **@no__t -4System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="58ad1-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="58ad1-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<authenticationModules >** ](authenticationmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="58ad1-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)</span></span>  
<span data-ttu-id="58ad1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Agregar >**</span><span class="sxs-lookup"><span data-stu-id="58ad1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58ad1-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58ad1-108">Syntax</span></span>  
  
```xml  
<add
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58ad1-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="58ad1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="58ad1-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="58ad1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58ad1-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="58ad1-111">Attributes</span></span>  
  
|<span data-ttu-id="58ad1-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="58ad1-112">**Attribute**</span></span>|<span data-ttu-id="58ad1-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="58ad1-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="58ad1-114">El nombre de tipo completo (indicado por la propiedad <xref:System.Type.FullName%2A>) y el nombre del ensamblado (indicado por la propiedad <xref:System.Reflection.Assembly.FullName%2A>), separados por una coma.</span><span class="sxs-lookup"><span data-stu-id="58ad1-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58ad1-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="58ad1-115">Child Elements</span></span>  
 <span data-ttu-id="58ad1-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="58ad1-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="58ad1-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="58ad1-117">Parent Elements</span></span>  
  
|<span data-ttu-id="58ad1-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="58ad1-118">**Element**</span></span>|<span data-ttu-id="58ad1-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="58ad1-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="58ad1-120">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="58ad1-120">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="58ad1-121">Especifica los módulos que se usan para autenticar las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="58ad1-121">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58ad1-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="58ad1-122">Remarks</span></span>  
 <span data-ttu-id="58ad1-123">El elemento `add` agrega un módulo de autenticación al final de la lista de módulos de autenticación registrados.</span><span class="sxs-lookup"><span data-stu-id="58ad1-123">The `add` element adds an authentication module to the end of the list of registered authentication modules.</span></span> <span data-ttu-id="58ad1-124">Los módulos de autenticación se llaman en el orden en que se agregaron a la lista.</span><span class="sxs-lookup"><span data-stu-id="58ad1-124">Authentication modules are called in the order in which they were added to the list.</span></span>  
  
 <span data-ttu-id="58ad1-125">El valor del atributo `type` debe ser un nombre de tipo válido y el nombre de ensamblado correspondiente, separados por una coma.</span><span class="sxs-lookup"><span data-stu-id="58ad1-125">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="58ad1-126">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="58ad1-126">Configuration Files</span></span>  
 <span data-ttu-id="58ad1-127">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="58ad1-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="58ad1-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="58ad1-128">Example</span></span>  
 <span data-ttu-id="58ad1-129">En el ejemplo siguiente se habilitan los módulos de autenticación predeterminados.</span><span class="sxs-lookup"><span data-stu-id="58ad1-129">The following example enables the default authentication modules.</span></span> <span data-ttu-id="58ad1-130">Debe reemplazar los valores de version y PublicKeyToken por los valores correctos para el módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="58ad1-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="58ad1-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="58ad1-131">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="58ad1-132">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="58ad1-132">Network Settings Schema</span></span>](index.md)
