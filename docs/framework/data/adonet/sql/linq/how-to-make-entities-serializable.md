---
description: 'Más información sobre: Cómo: hacer que las entidades sean serializables'
title: Procedimiento para serializar entidades
ms.date: 03/30/2017
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
ms.openlocfilehash: cb2253d7933f3584543b4b030bc8b5aa3cc62921
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785944"
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
