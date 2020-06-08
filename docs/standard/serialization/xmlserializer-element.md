---
title: <xmlSerializer> (Elemento)
description: El elemento <xmlSerializer> especifica si se realiza una comprobación adicional del progreso de XmlSerializer.
ms.date: 03/30/2017
helpviewer_keywords:
- <xmlSerializer> element
- XML serialization, configuration
- xmlSerializer element
ms.assetid: d129d10c-3eb7-45d9-8098-5fa853825e47
ms.openlocfilehash: 667d59f7eb0d1c7682afcdda584cc5b0ca2da802
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "84288932"
---
# <a name="xmlserializer-element"></a><span data-ttu-id="beee8-103">\<xmlSerializer> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="beee8-103">\<xmlSerializer> Element</span></span>
<span data-ttu-id="beee8-104">Especifica si se hace una comprobación adicional de progreso de <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="beee8-104">Specifies whether an additional check of progress of the <xref:System.Xml.Serialization.XmlSerializer> is done.</span></span>  
  
 \<configuration>  
\<system.xml.serialization>  
  
## <a name="syntax"></a><span data-ttu-id="beee8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="beee8-105">Syntax</span></span>  
  
```xml  
<xmlSerializer checkDeserializerAdvance = "true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="beee8-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="beee8-106">Attributes and Elements</span></span>  
 <span data-ttu-id="beee8-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="beee8-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="beee8-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="beee8-108">Attributes</span></span>  
  
|<span data-ttu-id="beee8-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="beee8-109">Attribute</span></span>|<span data-ttu-id="beee8-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="beee8-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="beee8-111">**checkDeserializeAdvances**</span><span class="sxs-lookup"><span data-stu-id="beee8-111">**checkDeserializeAdvances**</span></span>|<span data-ttu-id="beee8-112">Especifica si se comprueba el progreso de <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="beee8-112">Specifies whether the progress of the <xref:System.Xml.Serialization.XmlSerializer> is checked.</span></span> <span data-ttu-id="beee8-113">Establezca el atributo a "verdadero" o "falso."</span><span class="sxs-lookup"><span data-stu-id="beee8-113">Set the attribute to "true" or "false".</span></span> <span data-ttu-id="beee8-114">El valor predeterminado es "true".</span><span class="sxs-lookup"><span data-stu-id="beee8-114">The default is "true".</span></span>|  
|<span data-ttu-id="beee8-115">**useLegacySerializationGeneration**</span><span class="sxs-lookup"><span data-stu-id="beee8-115">**useLegacySerializationGeneration**</span></span>|<span data-ttu-id="beee8-116">Especifica si <xref:System.Xml.Serialization.XmlSerializer> usa generación de serialización heredada, que genera ensamblados escribiendo código de C# en un archivo y después compilándolo en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="beee8-116">Specifies whether the <xref:System.Xml.Serialization.XmlSerializer> uses legacy serialization generation which generates assemblies by writing C# code to a file and then compiling it to an assembly.</span></span> <span data-ttu-id="beee8-117">El valor predeterminado es **false**.</span><span class="sxs-lookup"><span data-stu-id="beee8-117">The default is **false**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="beee8-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="beee8-118">Child Elements</span></span>  
 <span data-ttu-id="beee8-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="beee8-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="beee8-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="beee8-120">Parent Elements</span></span>  
  
|<span data-ttu-id="beee8-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="beee8-121">Element</span></span>|<span data-ttu-id="beee8-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="beee8-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="beee8-123">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="beee8-123">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)|<span data-ttu-id="beee8-124">Contiene la configuración para <xref:System.Xml.Serialization.XmlSerializer> y las clases <xref:System.Xml.Serialization.XmlSchemaImporter>.</span><span class="sxs-lookup"><span data-stu-id="beee8-124">Contains configuration settings for the <xref:System.Xml.Serialization.XmlSerializer> and <xref:System.Xml.Serialization.XmlSchemaImporter> classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="beee8-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="beee8-125">Remarks</span></span>  
 <span data-ttu-id="beee8-126">De forma predeterminada, <xref:System.Xml.Serialization.XmlSerializer> proporciona una capa adicional de seguridad contra los ataques por denegación de servicio potenciales al deserializar datos que no son de confianza.</span><span class="sxs-lookup"><span data-stu-id="beee8-126">By default, the <xref:System.Xml.Serialization.XmlSerializer> provides an additional layer of security against potential denial of service attacks when deserializing untrusted data.</span></span> <span data-ttu-id="beee8-127">Actúa de esta modo intentando detectar los bucles sin fin durante la deserialización.</span><span class="sxs-lookup"><span data-stu-id="beee8-127">It does so by attempting to detect infinite loops during deserialization.</span></span> <span data-ttu-id="beee8-128">Si se detecta este tipo de condición, se inicia una excepción con el siguiente mensaje: "Error interno: la deserialización no ha podido avanzar sobre la secuencia subyacente".</span><span class="sxs-lookup"><span data-stu-id="beee8-128">If such a condition is detected, an exception is thrown with the following message: "Internal error: deserialization failed to advance over underlying stream."</span></span>  
  
 <span data-ttu-id="beee8-129">Recibir este mensaje necesariamente no indica que un ataque por denegación de servicio está en curso.</span><span class="sxs-lookup"><span data-stu-id="beee8-129">Receiving this message does not necessarily indicate that a denial of service attack is in progress.</span></span> <span data-ttu-id="beee8-130">En algunas circunstancias raras, el mecanismo de detección de bucle sin fin genera un positivo falso y la excepción se producirá para un mensaje entrante legítimo.</span><span class="sxs-lookup"><span data-stu-id="beee8-130">In some rare circumstances, the infinite loop detection mechanism produces a false positive and the exception is thrown for a legitimate incoming message.</span></span> <span data-ttu-id="beee8-131">Si detecta que en la aplicación concreta esta capa adicional de protección está rechazando los mensajes legítimos, establezca el atributo **checkDeserializeAdvances** en "false".</span><span class="sxs-lookup"><span data-stu-id="beee8-131">If you find that in your particular application legitimate messages are being rejected by this extra layer of protection, set **checkDeserializeAdvances** attribute to "false".</span></span>  
  
## <a name="example"></a><span data-ttu-id="beee8-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="beee8-132">Example</span></span>  
 <span data-ttu-id="beee8-133">En el ejemplo de código siguiente se establece el atributo **checkDeserializeAdvances** en "false".</span><span class="sxs-lookup"><span data-stu-id="beee8-133">The following code example sets the **checkDeserializeAdvances** attribute to "false".</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="beee8-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="beee8-134">See also</span></span>

- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="beee8-135">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="beee8-135">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
- [<span data-ttu-id="beee8-136">Serialización SOAP y XML</span><span class="sxs-lookup"><span data-stu-id="beee8-136">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
