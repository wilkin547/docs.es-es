---
title: Herramienta Generador de serializador XML (Sgen.exe)
ms.date: 03/30/2017
ms.assetid: cc1d1f1c-fb26-4be9-885a-3fe84c81cec6
ms.openlocfilehash: bc1a0abaeef9a9244aa83941e590063c7ef167d1
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588362"
---
# <a name="xml-serializer-generator-tool-sgenexe"></a>Herramienta Generador de serializador XML (Sgen.exe)

El Generador de serializador XML crea un ensamblado de serialización XML para los tipos de un ensamblado especificado. El ensamblado de serialización mejora el rendimiento de inicio de un elemento <xref:System.Xml.Serialization.XmlSerializer> al serializar o deserializar objetos de los tipos especificados.
  
## <a name="syntax"></a>Sintaxis

Ejecute la herramienta desde la línea de comandos.
  
```console  
sgen [options]  
```
  
> [!TIP]
> Para que las herramientas de .NET Framework funcionen correctamente, es necesario configurar correctamente las variables de entorno `Path`, `Include` y `Lib`. Establezca estas variables de entorno ejecutando SDKVars.bat, que se encuentra en el directorio \<SDK>\v2.0\Bin. SDKVars.bat debe ejecutarse en cada shell de comando.
  
## <a name="parameters"></a>Parámetros  
  
|Opción|Descripción|  
|------------|-----------------|  
|**/a\[ssembly\]:** _nombre_de_archivo_|Genera código de serialización para todos los tipos incluidos en el ensamblado o la aplicación ejecutable especificados por *filename*. Solo se puede proporcionar un nombre de archivo. Si se repite este argumento, se utilizará el último nombre.|  
|**/c\[ompiler\]:** _opciones_|Especifica las opciones que se deben pasar al compilador de C#. Todas las opciones de csc.exe se admiten tal como se pasan al compilador. Esto puede servir para especificar que se debería firmar el ensamblado, así como para especificar el archivo de clave.|  
|**/d\[ebug\]**|Genera un imagen que se puede utilizar con un depurador.|  
|**/f\[orce\]**|Exige que se sobrescriba un ensamblado existente que tenga el mismo nombre. El valor predeterminado es **false**.|  
|**/help o /?**|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
|**/k\[eep\]**|Suprime la eliminación de los archivos de código fuente generados y otros archivos temporales después de que se han compilado en el ensamblado de serialización. Puede servir para determinar si la herramienta genera código de serialización para un tipo determinado.|  
|**/n\[ologo\]**|Suprime la presentación de la portada de inicio de Microsoft.|  
|**/o\[ut\]:** _ruta_de_acceso_|Especifica el directorio en el que se debe guardar el ensamblado generado. **Nota:**  El nombre del ensamblado generado está compuesto por el nombre del ensamblado de entrada y "xmlSerializers.dll".|  
|**/p\[roxytypes\]**|Solo se genera código de serialización para los tipos de proxy de servicio Web XML.|  
|**/r\[eference\]:** _archivos_de_ensamblado_|Especifica los ensamblados a los que hacen referencia los tipos que requieren serialización XML. Acepta varios archivos de ensamblado separados por comas.|  
|**/s\[ilent\]**|Suprime la presentación de mensajes de aprobación.|  
|**/t\[ype\]:** _tipo_|Solo genera código de serialización para el tipo especificado.|  
|**/v\[erbose\]**|Muestra resultados detallados para la depuración. Enumera tipos del ensamblado de destino que no se pueden serializar con <xref:System.Xml.Serialization.XmlSerializer>.|  
|**/?**|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
  
## <a name="remarks"></a>Comentarios  
 Cuando no se utiliza el Generador de serializador XML, un objeto <xref:System.Xml.Serialization.XmlSerializer> genera código de serialización y un ensamblado de serialización para cada tipo siempre que se ejecuta una aplicación. Para mejorar el rendimiento del inicio de la serialización XML, use la herramienta Sgen.exe a fin de generar esos ensamblados con antelación. Estos ensamblados se podrán implementar después con la aplicación.  
  
 El Generador de serializador XML también puede mejorar el rendimiento de los clientes que utilizan proxy de servicio Web XML para comunicarse con los servidores, dado que no se verá afectado el rendimiento del proceso de serialización la primera vez que se carga el tipo.  
  
 Estos ensamblados generados no se pueden utilizar en el lado del servidor de un servicio Web. Esta herramienta solo es para los clientes de servicios Web y escenarios de serialización manual.  
  
 Si el ensamblado que contiene el tipo que se debe serializar se denomina MyType.dll, el ensamblado de serialización asociado se denominará MyType.XmlSerializers.dll.  
  
## <a name="examples"></a>Ejemplos  
 Mediante el siguiente comando se crea un ensamblado denominado Data.XmlSerializers.dll para serializar todos los tipos que contiene el ensamblado denominado Data.dll.  
  
```console  
sgen Data.dll
```  
  
 Se puede hacer referencia al ensamblado Data.XmlSerializers.dll desde código cuando se necesite serializar y deserializar los tipos en Data.dll.  
  
## <a name="see-also"></a>Vea también

- [Herramientas](../../../docs/framework/tools/index.md)
- [Símbolos del sistema](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
