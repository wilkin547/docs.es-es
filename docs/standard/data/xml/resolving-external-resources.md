---
title: Resolver recursos externos
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: ad3fa320-4b8f-4e5c-b549-01157591007a
ms.openlocfilehash: 05cc41cef7da07581d4f0ec8e584858b913d1a80
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710276"
---
# <a name="resolving-external-resources"></a>Resolver recursos externos
La clase **XmlDocument** utiliza la propiedad **XmlResolver** de **XmlDocument** para localizar recursos que no están alineados en los datos XML, como las definiciones de tipo de documento (DTD), entidades y esquemas externos. Estos elementos se pueden localizar en una red o en una unidad local, y se identifican mediante un identificador de recursos uniforme (URI). Esto permite a **XmlDocument** resolver los nodos **EntityReference** presentes en el documento y validar el documento de acuerdo con la DTD o el esquema externos.  
  
## <a name="fully-trusted-xmldocument"></a>XmlDocument de plena confianza  
 La propiedad **XmlResolver** afecta a la funcionalidad del método **XmlDocument.Load**. La tabla que aparece a continuación muestra cómo funciona la propiedad **XmlDocument.XmlResolver** cuando el objeto **XmlDocument** es de plena confianza. Esta tabla muestra los métodos **XmlDocument.Load** cuando la entrada para Load es **TextReader**, **String**, **Stream** o **URI**. Esta tabla no se aplica al método **Load** si **XmlDocument** se carga de **XmlReader**.  
  
|Propiedad XmlResolver|Función|Notas|  
|--------------------------|--------------|-----------|  
|La propiedad se establece en una clase **XmlResolver** que se ha creado previamente y que tiene las propiedades establecidas por el usuario.|El objeto **XmlDocument** utiliza la clase **XmlResolver** proporcionada para resolver nombres de archivo y referencias de recursos externos, como las DTD, entidades y esquemas.<br /><br /> La propiedad **XmlResolver** se utiliza también para resolver recursos externos que son necesarios cuando se agregan o se editan nodos del objeto **XmlDocument**.|La propiedad **XmlResolver** que se proporciona para el objeto **XmlDocument** es el sistema de resolución que se utiliza siempre que es necesario localizar y resolver recursos externos.|  
|La propiedad se establece en **null** (**Nothing** en Microsoft Visual Basic .NET).|No es compatible con ninguna de las características que requiere un recurso externo, como localizar un esquema o DTD externo. Tampoco resuelve entidades externas ni admite funciones de edición, como la inserción de nodos de entidad que requieren resolución.|El objeto **XmlDocument** utiliza permisos anónimos para cargar archivos y no intenta resolver ningún otro recurso.|  
|El valor de la propiedad no se establece, aunque se deja en su estado predeterminado.|Se crea una instancia de **XmlUrlResolver** con las credenciales NULL que utiliza el objeto **XmlDocument** al resolver nombres de archivo, localizar las DTD, entidades y esquemas externos; las credenciales **null** se utilizan al editar nodos.||  
  
 La tabla siguiente muestra el método **XmlDocument.Load** cuando la entrada para **Load** es **XmlReader** y el objeto **XmlDocument** es de plena confianza.  
  
|Propiedad XmlResolver|Función|Notas|  
|--------------------------|--------------|-----------|  
|La clase **XmlResolver** que utiliza el objeto **XmlDocument** es la misma clase que la que utiliza **XmlReader**.|El objeto **XmlDocument** utiliza la clase **XmlResolver** asignada a **XmlReader**.<br /><br /> No se puede establecer la propiedad **XmlDocument.Resolver**, independientemente del nivel de confianza de **XmlDocument** porque obtiene una clase **XmlResolver** de **XmlReader**. No se puede intentar invalidar la configuración **XmlReaders**' **XmlResolver** estableciendo la propiedad **XmlResolver** de **XmlDocument**.|La clase **XmlReader** puede ser **XmlTextReader**, **XmlValidatingReader** o un sistema de lectura personalizado. Si el sistema de lectura utilizado admite la resolución de entidades, las entidades externas se resuelven. Si el sistema de lectura que se ha pasado no admite las referencias de entidad, entonces no se resuelven.|  
  
## <a name="semi-trusted-xmldocument"></a>XmlDocument de confianza parcial  
 La tabla siguiente muestra cómo funciona la propiedad **XmlDocument.XmlResolver** cuando el objeto es de confianza parcial. Esta tabla se aplica a los métodos **XmlDocument.Load** cuando la entrada para Load es **TextReader**, **String**, **Stream** o **URI**. Esta tabla no se aplica al método **Load** si **XmlDocument** se carga de **XmlReader**.  
  
|Propiedad XmlResolver|Función|Notas|  
|--------------------------|--------------|-----------|  
|En el escenario de confianza parcial, la propiedad **XmlResolver** no se puede establecer en ningún otro valor distinto de null.|Se crea una instancia de **XmlUrlResolver** con las credenciales **NULL** que utiliza el objeto **XmlDocument** al resolver nombres de archivo, localizar las DTD, entidades y esquemas externos; las credenciales **NULL** se utilizan al editar nodos.|Este comportamiento es idéntico al que tiene la propiedad **XmlResolver** cuando no se establece y se deja en su estado predeterminado.<br /><br /> El objeto **XmlDocument** utiliza permisos anónimos para todas las acciones.|  
|La propiedad se establece en **null** (**Nothing** en Microsoft Visual Basic .NET).|No es compatible con ninguna de las características que requiere un recurso externo, como localizar un esquema o DTD externo. Tampoco resuelve entidades externas ni admite funciones de edición, como la inserción de nodos de entidad que requieren resolución.|Cuando el valor de la propiedad es **null** el comportamiento es el mismo, independientemente de que el objeto **XmlDocument** sea de plena confianza o de confianza parcial.|  
|El valor de la propiedad no se establece, aunque se deja en su estado predeterminado.|Se crea una instancia de **XmlUrlResolver** con las credenciales **NULL** que utiliza el objeto **XmlDocument** al resolver nombres de archivo, localizar las DTD, entidades y esquemas externos; las credenciales **NULL** se utilizan al editar nodos.|El objeto **XmlDocument** utiliza permisos anónimos para todas las acciones.|  
  
 Esta tabla se aplica al método **XmlDocument.Load** cuando la entrada para **Load** es **XmlReader** y el objeto **XmlDocument** es de confianza parcial.  
  
|Propiedad XmlResolver|Función|Notas|  
|--------------------------|--------------|-----------|  
|La clase **XmlResolver** que utiliza el objeto **XmlDocument** es la misma clase que la que utiliza **XmlReader**.|El objeto **XmlDocument** utiliza la clase **XmlResolver** asignada a **XmlReader**.<br /><br /> No se puede establecer la propiedad **XmlDocument.Resolver**, independientemente del nivel de confianza de **XmlDocument** porque obtiene una clase **XmlResolver** de **XmlReader**. No se puede intentar invalidar la configuración de **XmlReaders** **XmlResolver** estableciendo la propiedad **XmlResolver** de **XmlDocument**.|La clase **XmlReader** puede ser **XmlTextReader**, validando <xref:System.Xml.XmlReader>, o un lector de escritura personalizada. Si el sistema de lectura utilizado admite la resolución de entidades, las entidades externas se resuelven. Si el sistema de lectura que se ha pasado no admite las referencias de entidad, entonces no se resuelven.|  
  
 El ajuste de XmlResolver para contener las credenciales correctas permite el acceso a los recursos externos.  
  
> [!NOTE]
> No hay ninguna forma de recuperar el valor de la propiedad **XmlResolver**. Esto ayuda a evitar que un usuario vuelva a utilizar una propiedad **XmlResolver** en la que se hayan establecido credenciales. Además, si se utiliza una clase **XmlTextReader** o se valida <xref:System.Xml.XmlReader> para cargar **XmlDocument** y **XmlDocument** tiene un sistema de resolución establecido, los correspondientes a estos sistemas de lectura no son almacenados en caché por **XmlDocument** después de la fase **Load**, puesto que esto también presenta un riesgo de seguridad.  
  
 Para obtener más información, vea la sección Comentarios de la página de referencia de <xref:System.Xml.XmlResolver>.  
  
## <a name="see-also"></a>Vea también

- [Document Object Model (DOM) para XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
