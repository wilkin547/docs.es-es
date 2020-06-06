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
ms.openlocfilehash: 4181a045079bdb455a63ebda722dd6b0daf33c4d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155120"
---
# <a name="add-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="83d45-102">Elemento \<add> para authenticationModules (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="83d45-102">\<add> Element for authenticationModules (Network Settings)</span></span>
<span data-ttu-id="83d45-103">Agrega un módulo de autenticación a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="83d45-103">Adds an authentication module to the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="83d45-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83d45-104">Syntax</span></span>  
  
```xml  
<add
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83d45-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="83d45-105">Attributes and Elements</span></span>  
 <span data-ttu-id="83d45-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="83d45-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83d45-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="83d45-107">Attributes</span></span>  
  
|<span data-ttu-id="83d45-108">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="83d45-108">**Attribute**</span></span>|<span data-ttu-id="83d45-109">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="83d45-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="83d45-110">El nombre de tipo completo (indicado por la <xref:System.Type.FullName%2A> propiedad) y el nombre de ensamblado (indicado por la <xref:System.Reflection.Assembly.FullName%2A> propiedad), separados por una coma.</span><span class="sxs-lookup"><span data-stu-id="83d45-110">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="83d45-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="83d45-111">Child Elements</span></span>  
 <span data-ttu-id="83d45-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="83d45-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="83d45-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="83d45-113">Parent Elements</span></span>  
  
|<span data-ttu-id="83d45-114">**Element**</span><span class="sxs-lookup"><span data-stu-id="83d45-114">**Element**</span></span>|<span data-ttu-id="83d45-115">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="83d45-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="83d45-116">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="83d45-116">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="83d45-117">Especifica los módulos que se usan para autenticar las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="83d45-117">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83d45-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="83d45-118">Remarks</span></span>  
 <span data-ttu-id="83d45-119">El `add` elemento agrega un módulo de autenticación al final de la lista de módulos de autenticación registrados.</span><span class="sxs-lookup"><span data-stu-id="83d45-119">The `add` element adds an authentication module to the end of the list of registered authentication modules.</span></span> <span data-ttu-id="83d45-120">Los módulos de autenticación se llaman en el orden en que se agregaron a la lista.</span><span class="sxs-lookup"><span data-stu-id="83d45-120">Authentication modules are called in the order in which they were added to the list.</span></span>  
  
 <span data-ttu-id="83d45-121">El valor del `type` atributo debe ser un nombre de tipo válido y el nombre de ensamblado correspondiente, separados por una coma.</span><span class="sxs-lookup"><span data-stu-id="83d45-121">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="83d45-122">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="83d45-122">Configuration Files</span></span>  
 <span data-ttu-id="83d45-123">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="83d45-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="83d45-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="83d45-124">Example</span></span>  
 <span data-ttu-id="83d45-125">En el ejemplo siguiente se habilitan los módulos de autenticación predeterminados.</span><span class="sxs-lookup"><span data-stu-id="83d45-125">The following example enables the default authentication modules.</span></span> <span data-ttu-id="83d45-126">Debe reemplazar los valores de version y PublicKeyToken por los valores correctos para el módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="83d45-126">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="83d45-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="83d45-127">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="83d45-128">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="83d45-128">Network Settings Schema</span></span>](index.md)
