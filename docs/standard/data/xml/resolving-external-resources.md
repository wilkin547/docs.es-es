---
title: Resolver recursos externos
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad3fa320-4b8f-4e5c-b549-01157591007a
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 824a35ee5d4ecafc45167ff3f4bc89802af4ed96
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="resolving-external-resources"></a>Resolver recursos externos
El **XmlResolver** propiedad de la **XmlDocument** utiliza la **XmlDocument** clase para localizar recursos que no están en línea en los datos XML, como el tipo de documento externo definiciones (DTD), entidades y esquemas. Estos elementos se pueden localizar en una red o en una unidad local, y se identifican mediante un identificador de recursos uniforme (URI). Esto permite la **XmlDocument** para resolver **EntityReference** nodos que están presentes en el documento y validar el documento de acuerdo con la DTD o esquema externo.  
  
## <a name="fully-trusted-xmldocument"></a>XmlDocument de plena confianza  
 El **XmlResolver** propiedad afecta a la funcionalidad de la **XmlDocument.Load** método. La tabla siguiente se muestra cómo el **XmlDocument.XmlResolver** propiedad funciona cuando la **XmlDocument** objeto es de plena confianza. La tabla siguiente muestra la **XmlDocument.Load** métodos cuando la entrada para Load es un **TextReader**, **cadena**, **flujo**, o  **URI**. Esta tabla no se aplica a la **carga** método si la **XmlDocument** se carga desde un **XmlReader**.  
  
|Propiedad XmlResolver|Función|Notas|  
|--------------------------|--------------|-----------|  
|La propiedad se establece en un **XmlResolver** clase que se ha creado anteriormente y tiene propiedades establecidas por el usuario.|El **XmlDocument** utiliza la **XmlResolver** proporcionada para resolver nombres de archivo para resolver las referencias a recursos externos, como las DTD, entidades y esquemas.<br /><br /> El **XmlResolver** también se utiliza para resolver recursos externos que son necesarios al agregar o editar nodos en el **XmlDocument**.|El **XmlResolver** dado a la **XmlDocument** es la resolución que se utiliza siempre que sea necesario localizar y resolver recursos externos.|  
|La propiedad se establece en **null** (**nada** en Microsoft Visual Basic. NET).|No es compatible con ninguna de las características que requiere un recurso externo, como localizar un esquema o DTD externo. Tampoco resuelve entidades externas ni admite funciones de edición, como la inserción de nodos de entidad que requieren resolución.|El **XmlDocument** cargar archivos anónimos y no intenta resolver ningún otro recurso.|  
|El valor de la propiedad no se establece, aunque se deja en su estado predeterminado.|Un **XmlUrlResolver** con NULL credenciales se crea y se usa el **XmlDocument** al resolver nombres de archivo, localizar las DTD, entidades y esquemas, externas y **null** las credenciales se utilizan al editar nodos.||  
  
 La tabla siguiente muestra la **XmlDocument.Load** método cuando la entrada para el **carga** es un **XmlReader** y la **XmlDocument** es plena confianza.  
  
|Propiedad XmlResolver|Función|Notas|  
|--------------------------|--------------|-----------|  
|El **XmlResolver** clase usada por la **XmlDocument** es la misma clase que usa el **XmlReader**.|El **XmlDocument** utiliza la **XmlResolver** que se asignó a la **XmlReader**.<br /><br /> El **XmlDocument.Resolver** propiedad no se puede establecer, sin tener en cuenta el **XmlDocument** nivel de confianza porque obtiene una **XmlResolver** desde el  **XmlReader**. No se puede intentar invalidar la configuración de la **XmlReaders**' **XmlResolver** estableciendo la **XmlResolver** propiedad de la **XmlDocument**.|El **XmlReader** puede ser el **XmlTextReader**, **XmlValidatingReader**, o un sistema de lectura personalizado. Si el sistema de lectura utilizado admite la resolución de entidades, las entidades externas se resuelven. Si el sistema de lectura que se ha pasado no admite las referencias de entidad, entonces no se resuelven.|  
  
## <a name="semi-trusted-xmldocument"></a>XmlDocument de confianza parcial  
 La tabla siguiente muestra cómo el **XmlDocument.XmlResolver** propiedad funciona cuando el objeto es de confianza parcial. Esta tabla se aplica a la **XmlDocument.Load** métodos cuando la entrada para Load es un **TextReader**, **cadena**, **flujo**, o  **URI**. Esta tabla no se aplica a la **carga** método si la **XmlDocument** se carga desde un **XmlReader**.  
  
|Propiedad XmlResolver|Función|Notas|  
|--------------------------|--------------|-----------|  
|En el escenario de confianza parcial, el **XmlResolver** no se puede establecer la propiedad en un valor distinto de null.|Un **XmlUrlResolver** con **null** credenciales se crea una instancia y se usa el **XmlDocument** al resolver nombres de archivo, localizar las DTD externas, entidades, y esquemas, y **null** credenciales se utilizan al editar nodos.|Este comportamiento es idéntico al comportamiento cuando la **XmlResolver** propiedad no se establece, aunque se deja en su estado predeterminado.<br /><br /> El **XmlDocument** utiliza permisos anónimos para todas las acciones.|  
|La propiedad se establece en **null** (**nada** en Microsoft Visual Basic. NET).|No es compatible con ninguna de las características que requiere un recurso externo, como localizar un esquema o DTD externo. Tampoco resuelve entidades externas ni admite funciones de edición, como la inserción de nodos de entidad que requieren resolución.|Cuando la propiedad es **null**, el comportamiento es el mismo independientemente de que el **XmlDocument** sea de plena confianza o de confianza parcial.|  
|El valor de la propiedad no se establece, aunque se deja en su estado predeterminado.|Un **XmlUrlResolver** con **null** credenciales se crea una instancia y se usa el **XmlDocument** al resolver nombres de archivo, localizar las DTD externas, entidades, y esquemas, y **null** credenciales se utilizan al editar nodos.|El **XmlDocument** utiliza permisos anónimos para todas las acciones.|  
  
 Esta tabla se aplica a la **XmlDocument.Load** método cuando la entrada para el **carga** es un **XmlReader**y el **XmlDocument** es confianza parcial.  
  
|Propiedad XmlResolver|Función|Notas|  
|--------------------------|--------------|-----------|  
|El **XmlResolver** clase usada por la **XmlDocument** es el mismo que se está usando el **XmlReader**.|El **XmlDocument** utiliza la **XmlResolver** que se asignó a la **XmlReader**.<br /><br /> El **XmlDocument.Resolver** propiedad no se puede establecer, sin tener en cuenta el **XmlDocument** nivel de confianza porque obtiene una **XmlResolver** desde el  **XmlReader**. No se puede intentar invalidar la configuración de la **XmlReaders** **XmlResolver** estableciendo la **XmlResolver** propiedad de la **XmlDocument**.|El **XmlReader** puede ser el **XmlTextReader**, validando <xref:System.Xml.XmlReader>, o un sistema de lectura personalizado. Si el sistema de lectura utilizado admite la resolución de entidades, las entidades externas se resuelven. Si el sistema de lectura que se ha pasado no admite las referencias de entidad, entonces no se resuelven.|  
  
 El ajuste de XmlResolver para contener las credenciales correctas permite el acceso a los recursos externos.  
  
> [!NOTE]
>  No hay ninguna manera de recuperar el **XmlResolver** propiedad. Esto ayuda a evitar que un usuario vuelva a emplear un **XmlResolver** en las credenciales que se hayan establecido. Además, si un **XmlTextReader** o validar <xref:System.Xml.XmlReader> se usa para cargar la **XmlDocument** y **XmlDocument** tiene una resolución que se ha establecido, las resoluciones de estos lectores no se almacenan en caché por la **XmlDocument** después de la **carga** fase, puesto que esto también presenta un riesgo de seguridad.  
  
 Para obtener más información, vea la sección Comentarios de la página de referencia de <xref:System.Xml.XmlResolver>.  
  
## <a name="see-also"></a>Vea también  
 [Modelo de objetos de documento (DOM) de XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
