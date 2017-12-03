---
title: '&lt;xmlSerializer&gt; (Elemento)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <xmlSerializer> element
- XML serialization, configuration
- xmlSerializer element
ms.assetid: d129d10c-3eb7-45d9-8098-5fa853825e47
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 17e4fcd1b471a5197f2e6a30bad10cbdbe22f216
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltxmlserializergt-element"></a><span data-ttu-id="464c2-102">&lt;xmlSerializer&gt; (Elemento)</span><span class="sxs-lookup"><span data-stu-id="464c2-102">&lt;xmlSerializer&gt; Element</span></span>
<span data-ttu-id="464c2-103">Especifica si se hace una comprobación adicional de progreso de <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="464c2-103">Specifies whether an additional check of progress of the <xref:System.Xml.Serialization.XmlSerializer> is done.</span></span>  
  
 <span data-ttu-id="464c2-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="464c2-104">\<configuration></span></span>  
<span data-ttu-id="464c2-105">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="464c2-105">\<system.xml.serialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="464c2-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="464c2-106">Syntax</span></span>  
  
```xml  
<xmlSerializer checkDeserializerAdvance = "true"|"false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="464c2-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="464c2-107">Attributes and Elements</span></span>  
 <span data-ttu-id="464c2-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="464c2-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="464c2-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="464c2-109">Attributes</span></span>  
  
|<span data-ttu-id="464c2-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="464c2-110">Attribute</span></span>|<span data-ttu-id="464c2-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="464c2-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="464c2-112">**checkDeserializeAdvances**</span><span class="sxs-lookup"><span data-stu-id="464c2-112">**checkDeserializeAdvances**</span></span>|<span data-ttu-id="464c2-113">Especifica si se comprueba el progreso de <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="464c2-113">Specifies whether the progress of the <xref:System.Xml.Serialization.XmlSerializer> is checked.</span></span> <span data-ttu-id="464c2-114">Establezca el atributo a "verdadero" o "falso."</span><span class="sxs-lookup"><span data-stu-id="464c2-114">Set the attribute to "true" or "false".</span></span> <span data-ttu-id="464c2-115">El valor predeterminado es "true".</span><span class="sxs-lookup"><span data-stu-id="464c2-115">The default is "true".</span></span>|  
|<span data-ttu-id="464c2-116">**useLegacySerializationGeneration**</span><span class="sxs-lookup"><span data-stu-id="464c2-116">**useLegacySerializationGeneration**</span></span>|<span data-ttu-id="464c2-117">Especifica si <xref:System.Xml.Serialization.XmlSerializer> usa generación de serialización heredada, que genera ensamblados escribiendo código de C# en un archivo y después compilándolo en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="464c2-117">Specifies whether the <xref:System.Xml.Serialization.XmlSerializer> uses legacy serialization generation which generates assemblies by writing C# code to a file and then compiling it to an assembly.</span></span> <span data-ttu-id="464c2-118">El valor predeterminado es **false**.</span><span class="sxs-lookup"><span data-stu-id="464c2-118">The default is **false**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="464c2-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="464c2-119">Child Elements</span></span>  
 <span data-ttu-id="464c2-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="464c2-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="464c2-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="464c2-121">Parent Elements</span></span>  
  
|<span data-ttu-id="464c2-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="464c2-122">Element</span></span>|<span data-ttu-id="464c2-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="464c2-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="464c2-124">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="464c2-124">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="464c2-125">Contiene la configuración para <xref:System.Xml.Serialization.XmlSerializer> y las clases <xref:System.Xml.Serialization.XmlSchemaImporter>.</span><span class="sxs-lookup"><span data-stu-id="464c2-125">Contains configuration settings for the <xref:System.Xml.Serialization.XmlSerializer> and <xref:System.Xml.Serialization.XmlSchemaImporter> classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="464c2-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="464c2-126">Remarks</span></span>  
 <span data-ttu-id="464c2-127">De forma predeterminada, <xref:System.Xml.Serialization.XmlSerializer> proporciona una capa adicional de seguridad contra los ataques por denegación de servicio potenciales al deserializar datos que no son de confianza.</span><span class="sxs-lookup"><span data-stu-id="464c2-127">By default, the <xref:System.Xml.Serialization.XmlSerializer> provides an additional layer of security against potential denial of service attacks when deserializing untrusted data.</span></span> <span data-ttu-id="464c2-128">Actúa de esta modo intentando detectar los bucles sin fin durante la deserialización.</span><span class="sxs-lookup"><span data-stu-id="464c2-128">It does so by attempting to detect infinite loops during deserialization.</span></span> <span data-ttu-id="464c2-129">Si se detecta este tipo de condición, se produce una excepción con el mensaje siguiente: "Error interno: la deserialización no pudo sobrepasar el flujo subyacente".</span><span class="sxs-lookup"><span data-stu-id="464c2-129">If such a condition is detected, an exception is thrown with the following message: "Internal error: deserialization failed to advance over underlying stream."</span></span>  
  
 <span data-ttu-id="464c2-130">Recibir este mensaje necesariamente no indica que un ataque por denegación de servicio está en curso.</span><span class="sxs-lookup"><span data-stu-id="464c2-130">Receiving this message does not necessarily indicate that a denial of service attack is in progress.</span></span> <span data-ttu-id="464c2-131">En algunas circunstancias raras, el mecanismo de detección de bucle sin fin genera un positivo falso y la excepción se producirá para un mensaje entrante legítimo.</span><span class="sxs-lookup"><span data-stu-id="464c2-131">In some rare circumstances, the infinite loop detection mechanism produces a false positive and the exception is thrown for a legitimate incoming message.</span></span> <span data-ttu-id="464c2-132">Si detecta que en la aplicación concreta esta capa adicional de protección está rechazando los mensajes legítimos, establezca el atributo **checkDeserializeAdvances** en "false".</span><span class="sxs-lookup"><span data-stu-id="464c2-132">If you find that in your particular application legitimate messages are being rejected by this extra layer of protection, set **checkDeserializeAdvances** attribute to "false".</span></span>  
  
## <a name="example"></a><span data-ttu-id="464c2-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="464c2-133">Example</span></span>  
 <span data-ttu-id="464c2-134">En el ejemplo de código siguiente se establece el atributo **checkDeserializeAdvances** en "false".</span><span class="sxs-lookup"><span data-stu-id="464c2-134">The following code example sets the **checkDeserializeAdvances** attribute to "false".</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="464c2-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="464c2-135">See Also</span></span>  
 <xref:System.Xml.Serialization.XmlSerializer>  
 [<span data-ttu-id="464c2-136">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="464c2-136">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)  
 [<span data-ttu-id="464c2-137">Serialización SOAP y XML</span><span class="sxs-lookup"><span data-stu-id="464c2-137">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
