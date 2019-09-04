---
title: <system.identityModel>
ms.date: 03/30/2017
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
author: BrucePerlerMS
ms.openlocfilehash: a54f5ce86aee1a5e831c0b10aa1471d4a82f40a5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251790"
---
# <a name="systemidentitymodel"></a><span data-ttu-id="5a695-102">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="5a695-102">\<system.identityModel></span></span>
<span data-ttu-id="5a695-103">Proporciona la configuración para habilitar las opciones de Windows Identity Foundation (WIF) en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="5a695-103">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>  
  
<span data-ttu-id="5a695-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5a695-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5a695-105">&nbsp;&nbsp; **\<System. identityModel >**</span><span class="sxs-lookup"><span data-stu-id="5a695-105">&nbsp;&nbsp;**\<system.identityModel>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a695-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a695-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a695-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5a695-107">Attributes and Elements</span></span>  
 <span data-ttu-id="5a695-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5a695-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a695-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="5a695-109">Attributes</span></span>  
 <span data-ttu-id="5a695-110">None</span><span class="sxs-lookup"><span data-stu-id="5a695-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5a695-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5a695-111">Child Elements</span></span>  
  
|<span data-ttu-id="5a695-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="5a695-112">Element</span></span>|<span data-ttu-id="5a695-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5a695-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5a695-114">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="5a695-114">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="5a695-115">Especifica la configuración de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="5a695-115">Specifies service-level identity settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5a695-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5a695-116">Parent Elements</span></span>  
  
|<span data-ttu-id="5a695-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="5a695-117">Element</span></span>|<span data-ttu-id="5a695-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5a695-118">Description</span></span>|  
|-------------|-----------------|  
|`<configuration>`|<span data-ttu-id="5a695-119">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5a695-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a695-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5a695-120">Remarks</span></span>  
 <span data-ttu-id="5a695-121">Agregue una `<system.identityModel>` sección al archivo de configuración para configurar un servicio o una aplicación para usar Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="5a695-121">Add a `<system.identityModel>` section to the configuration file to configure a service or application to use Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="5a695-122">El elemento se representa mediante la <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> clase. `<system.identityModel>`</span><span class="sxs-lookup"><span data-stu-id="5a695-122">The `<system.identityModel>` element is represented by the <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a695-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5a695-123">Example</span></span>  
 <span data-ttu-id="5a695-124">En el ejemplo siguiente se muestra cómo agregar `<system.identityModel>` una sección a un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="5a695-124">The following example shows how to add a `<system.identityModel>` section to a configuration file.</span></span> <span data-ttu-id="5a695-125">Primero debe agregar la sección de configuración y la declaración de espacio `<configSections>` de nombres en el elemento.</span><span class="sxs-lookup"><span data-stu-id="5a695-125">You must first add the configuration section and namespace declaration under the `<configSections>` element.</span></span> <span data-ttu-id="5a695-126">Después, puede Agregar el `<system.IdentityModel>` elemento al archivo de configuración para especificar una o más configuraciones de identidad.</span><span class="sxs-lookup"><span data-stu-id="5a695-126">Then you can add the `<system.IdentityModel>` element to your configuration file to specify one or more identity configurations.</span></span>  
  
```xml  
<configuration>  
  <configSections>  
    <!--WIF 4.5 sections -->  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
  </configSections>  
  
  ...  
  
  <system.identityModel>  
    <identityConfiguration>  
      <audienceUris>  
        <add value="http://localhost/WebApplication1/" />  
      </audienceUris>  
      <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089">  
        <trustedIssuers>  
          <add thumbprint="313D3B … 9106A9EC" name="SelfSTS" />  
        </trustedIssuers>  
      </issuerNameRegistry>  
      <certificateValidation certificateValidationMode="None"/>  
    </identityConfiguration>  
  </system.identityModel>  
  
  ...  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5a695-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a695-127">See also</span></span>

- <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
