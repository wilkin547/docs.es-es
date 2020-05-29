---
title: <xmlSerializer> (Elemento)
description: El elemento <xmlSerializer> especifica si se realiza una comprobación adicional del progreso de XmlSerializer.
ms.date: 03/30/2017
helpviewer_keywords:
- <xmlSerializer> element
- XML serialization, configuration
- xmlSerializer element
ms.assetid: d129d10c-3eb7-45d9-8098-5fa853825e47
ms.openlocfilehash: 68037959893ec307a896ea86d21e40a9d7aa824c
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83380033"
---
# <a name="xmlserializer-element"></a><span data-ttu-id="04408-103">\<xmlSerializer> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="04408-103">\<xmlSerializer> Element</span></span>
<span data-ttu-id="04408-104">Especifica si se hace una comprobación adicional de progreso de <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="04408-104">Specifies whether an additional check of progress of the <xref:System.Xml.Serialization.XmlSerializer> is done.</span></span>  
  
 <span data-ttu-id="04408-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="04408-105">\<configuration></span></span>  
<span data-ttu-id="04408-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="04408-106">\<system.xml.serialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04408-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04408-107">Syntax</span></span>  
  
```xml  
<xmlSerializer checkDeserializerAdvance = "true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04408-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="04408-108">Attributes and Elements</span></span>  
 <span data-ttu-id="04408-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="04408-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04408-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="04408-110">Attributes</span></span>  
  
|<span data-ttu-id="04408-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="04408-111">Attribute</span></span>|<span data-ttu-id="04408-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="04408-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="04408-113">**checkDeserializeAdvances**</span><span class="sxs-lookup"><span data-stu-id="04408-113">**checkDeserializeAdvances**</span></span>|<span data-ttu-id="04408-114">Especifica si se comprueba el progreso de <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="04408-114">Specifies whether the progress of the <xref:System.Xml.Serialization.XmlSerializer> is checked.</span></span> <span data-ttu-id="04408-115">Establezca el atributo a "verdadero" o "falso."</span><span class="sxs-lookup"><span data-stu-id="04408-115">Set the attribute to "true" or "false".</span></span> <span data-ttu-id="04408-116">El valor predeterminado es "true".</span><span class="sxs-lookup"><span data-stu-id="04408-116">The default is "true".</span></span>|  
|<span data-ttu-id="04408-117">**useLegacySerializationGeneration**</span><span class="sxs-lookup"><span data-stu-id="04408-117">**useLegacySerializationGeneration**</span></span>|<span data-ttu-id="04408-118">Especifica si <xref:System.Xml.Serialization.XmlSerializer> usa generación de serialización heredada, que genera ensamblados escribiendo código de C# en un archivo y después compilándolo en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="04408-118">Specifies whether the <xref:System.Xml.Serialization.XmlSerializer> uses legacy serialization generation which generates assemblies by writing C# code to a file and then compiling it to an assembly.</span></span> <span data-ttu-id="04408-119">El valor predeterminado es **false**.</span><span class="sxs-lookup"><span data-stu-id="04408-119">The default is **false**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="04408-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="04408-120">Child Elements</span></span>  
 <span data-ttu-id="04408-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="04408-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="04408-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="04408-122">Parent Elements</span></span>  
  
|<span data-ttu-id="04408-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="04408-123">Element</span></span>|<span data-ttu-id="04408-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="04408-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="04408-125">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="04408-125">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="04408-126">Contiene la configuración para <xref:System.Xml.Serialization.XmlSerializer> y las clases <xref:System.Xml.Serialization.XmlSchemaImporter>.</span><span class="sxs-lookup"><span data-stu-id="04408-126">Contains configuration settings for the <xref:System.Xml.Serialization.XmlSerializer> and <xref:System.Xml.Serialization.XmlSchemaImporter> classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04408-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="04408-127">Remarks</span></span>  
 <span data-ttu-id="04408-128">De forma predeterminada, <xref:System.Xml.Serialization.XmlSerializer> proporciona una capa adicional de seguridad contra los ataques por denegación de servicio potenciales al deserializar datos que no son de confianza.</span><span class="sxs-lookup"><span data-stu-id="04408-128">By default, the <xref:System.Xml.Serialization.XmlSerializer> provides an additional layer of security against potential denial of service attacks when deserializing untrusted data.</span></span> <span data-ttu-id="04408-129">Actúa de esta modo intentando detectar los bucles sin fin durante la deserialización.</span><span class="sxs-lookup"><span data-stu-id="04408-129">It does so by attempting to detect infinite loops during deserialization.</span></span> <span data-ttu-id="04408-130">Si se detecta este tipo de condición, se inicia una excepción con el siguiente mensaje: "Error interno: la deserialización no ha podido avanzar sobre la secuencia subyacente".</span><span class="sxs-lookup"><span data-stu-id="04408-130">If such a condition is detected, an exception is thrown with the following message: "Internal error: deserialization failed to advance over underlying stream."</span></span>  
  
 <span data-ttu-id="04408-131">Recibir este mensaje necesariamente no indica que un ataque por denegación de servicio está en curso.</span><span class="sxs-lookup"><span data-stu-id="04408-131">Receiving this message does not necessarily indicate that a denial of service attack is in progress.</span></span> <span data-ttu-id="04408-132">En algunas circunstancias raras, el mecanismo de detección de bucle sin fin genera un positivo falso y la excepción se producirá para un mensaje entrante legítimo.</span><span class="sxs-lookup"><span data-stu-id="04408-132">In some rare circumstances, the infinite loop detection mechanism produces a false positive and the exception is thrown for a legitimate incoming message.</span></span> <span data-ttu-id="04408-133">Si detecta que en la aplicación concreta esta capa adicional de protección está rechazando los mensajes legítimos, establezca el atributo **checkDeserializeAdvances** en "false".</span><span class="sxs-lookup"><span data-stu-id="04408-133">If you find that in your particular application legitimate messages are being rejected by this extra layer of protection, set **checkDeserializeAdvances** attribute to "false".</span></span>  
  
## <a name="example"></a><span data-ttu-id="04408-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="04408-134">Example</span></span>  
 <span data-ttu-id="04408-135">En el ejemplo de código siguiente se establece el atributo **checkDeserializeAdvances** en "false".</span><span class="sxs-lookup"><span data-stu-id="04408-135">The following code example sets the **checkDeserializeAdvances** attribute to "false".</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="04408-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="04408-136">See also</span></span>

- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="04408-137">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="04408-137">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
- [<span data-ttu-id="04408-138">Serialización SOAP y XML</span><span class="sxs-lookup"><span data-stu-id="04408-138">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
