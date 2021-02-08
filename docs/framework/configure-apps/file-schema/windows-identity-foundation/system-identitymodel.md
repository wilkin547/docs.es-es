---
description: 'Más información acerca de: <System. identityModel>'
title: <system.identityModel>
ms.date: 03/30/2017
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
author: BrucePerlerMS
ms.openlocfilehash: c597f2a849248366f9cf3847c8ef369c13d7a286
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786530"
---
# \<system.identityModel>

<span data-ttu-id="214da-103">Proporciona la configuración para habilitar las opciones de Windows Identity Foundation (WIF) en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="214da-103">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.identityModel>**  
  
## <a name="syntax"></a><span data-ttu-id="214da-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="214da-104">Syntax</span></span>  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="214da-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="214da-105">Attributes and Elements</span></span>  

 <span data-ttu-id="214da-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="214da-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="214da-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="214da-107">Attributes</span></span>  

 <span data-ttu-id="214da-108">None</span><span class="sxs-lookup"><span data-stu-id="214da-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="214da-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="214da-109">Child Elements</span></span>  
  
|<span data-ttu-id="214da-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="214da-110">Element</span></span>|<span data-ttu-id="214da-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="214da-111">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="214da-112">Especifica la configuración de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="214da-112">Specifies service-level identity settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="214da-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="214da-113">Parent Elements</span></span>  
  
|<span data-ttu-id="214da-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="214da-114">Element</span></span>|<span data-ttu-id="214da-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="214da-115">Description</span></span>|  
|-------------|-----------------|  
|`<configuration>`|<span data-ttu-id="214da-116">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="214da-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="214da-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="214da-117">Remarks</span></span>  

 <span data-ttu-id="214da-118">Agregue una `<system.identityModel>` sección al archivo de configuración para configurar un servicio o una aplicación para usar Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="214da-118">Add a `<system.identityModel>` section to the configuration file to configure a service or application to use Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="214da-119">El `<system.identityModel>` elemento se representa mediante la <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> clase.</span><span class="sxs-lookup"><span data-stu-id="214da-119">The `<system.identityModel>` element is represented by the <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="214da-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="214da-120">Example</span></span>  

 <span data-ttu-id="214da-121">En el ejemplo siguiente se muestra cómo agregar una `<system.identityModel>` sección a un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="214da-121">The following example shows how to add a `<system.identityModel>` section to a configuration file.</span></span> <span data-ttu-id="214da-122">Primero debe agregar la sección de configuración y la declaración de espacio de nombres en el `<configSections>` elemento.</span><span class="sxs-lookup"><span data-stu-id="214da-122">You must first add the configuration section and namespace declaration under the `<configSections>` element.</span></span> <span data-ttu-id="214da-123">Después, puede Agregar el `<system.IdentityModel>` elemento al archivo de configuración para especificar una o más configuraciones de identidad.</span><span class="sxs-lookup"><span data-stu-id="214da-123">Then you can add the `<system.IdentityModel>` element to your configuration file to specify one or more identity configurations.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="214da-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="214da-124">See also</span></span>

- <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
