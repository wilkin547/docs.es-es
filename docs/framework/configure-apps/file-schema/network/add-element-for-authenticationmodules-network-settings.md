---
title: <add> (Elemento para authenticationModules, Configuración de red)
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
ms.openlocfilehash: 12dc8be762e1158ddaabbd67e7165d7bdaca6461
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55276333"
---
# <a name="add-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="02db1-102">\<Agregar > elemento para authenticationModules (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="02db1-102">\<add> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="02db1-103">Agrega un módulo de autenticación a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="02db1-103">Adds an authentication module to the application.</span></span>  
  
 <span data-ttu-id="02db1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="02db1-104">\<configuration></span></span>  
<span data-ttu-id="02db1-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="02db1-105">\<system.net></span></span>  
<span data-ttu-id="02db1-106">\<authenticationModules></span><span class="sxs-lookup"><span data-stu-id="02db1-106">\<authenticationModules></span></span>  
<span data-ttu-id="02db1-107">\<add></span><span class="sxs-lookup"><span data-stu-id="02db1-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02db1-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02db1-108">Syntax</span></span>  
  
```xml  
<add
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02db1-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="02db1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="02db1-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="02db1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02db1-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="02db1-111">Attributes</span></span>  
  
|<span data-ttu-id="02db1-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="02db1-112">**Attribute**</span></span>|<span data-ttu-id="02db1-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="02db1-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="02db1-114">El nombre de tipo completo (indicado por el <xref:System.Type.FullName%2A> propiedad) y el nombre del ensamblado (indicado por el <xref:System.Reflection.Assembly.FullName%2A> propiedad), separados por punto y coma.</span><span class="sxs-lookup"><span data-stu-id="02db1-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02db1-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="02db1-115">Child Elements</span></span>  
 <span data-ttu-id="02db1-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="02db1-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="02db1-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="02db1-117">Parent Elements</span></span>  
  
|<span data-ttu-id="02db1-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="02db1-118">**Element**</span></span>|<span data-ttu-id="02db1-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="02db1-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="02db1-120">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="02db1-120">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="02db1-121">Especifica los módulos que se usa para autenticar las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="02db1-121">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02db1-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="02db1-122">Remarks</span></span>  
 <span data-ttu-id="02db1-123">El `add` elemento agrega un módulo de autenticación al final de la lista de módulos de autenticación registrados.</span><span class="sxs-lookup"><span data-stu-id="02db1-123">The `add` element adds an authentication module to the end of the list of registered authentication modules.</span></span> <span data-ttu-id="02db1-124">Módulos de autenticación se llaman en el orden en que se agregaron a la lista.</span><span class="sxs-lookup"><span data-stu-id="02db1-124">Authentication modules are called in the order in which they were added to the list.</span></span>  
  
 <span data-ttu-id="02db1-125">El valor de la `type` atributo debe ser un nombre de tipo válido y el nombre de ensamblado correspondiente, separados por comas.</span><span class="sxs-lookup"><span data-stu-id="02db1-125">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="02db1-126">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="02db1-126">Configuration Files</span></span>  
 <span data-ttu-id="02db1-127">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="02db1-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="02db1-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="02db1-128">Example</span></span>  
 <span data-ttu-id="02db1-129">El ejemplo siguiente habilita los módulos de autenticación predeterminados.</span><span class="sxs-lookup"><span data-stu-id="02db1-129">The following example enables the default authentication modules.</span></span> <span data-ttu-id="02db1-130">Debe reemplazar los valores de versión y PublicKeyToken con los valores correctos para el módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="02db1-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="02db1-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="02db1-131">See also</span></span>
- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="02db1-132">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="02db1-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
