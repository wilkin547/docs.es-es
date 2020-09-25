---
title: Procedimiento para serializar entidades
ms.date: 03/30/2017
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
ms.openlocfilehash: f4528cab21ac678f5d06717d0ce6e7ff7e77d3e4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203506"
---
# <a name="how-to-make-entities-serializable"></a>Procedimiento para serializar entidades

Puede hacer que las entidades sean serializables al generar el código. Las clases de entidad se decoran con el atributo <xref:System.Runtime.Serialization.DataContractAttribute> y las columnas con el atributo <xref:System.Runtime.Serialization.DataMemberAttribute>.  
  
 Los desarrolladores que usan Visual Studio pueden usar el Object Relational Designer para este fin.  
  
 Si usa la herramienta de línea de comandos de SQLMetal, use la opción **/Serialization** con el `unidirectional` argumento. Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Ejemplo  

 Con las siguientes líneas de comandos de SQLMetal se generan archivos que tienen entidades serializables.  
  
```console  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```console  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a>Vea también

- [Serialización](serialization.md)
- [Crear el modelo de objetos](creating-the-object-model.md)
