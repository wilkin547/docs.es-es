---
title: 'Cómo: Validar archivos DBML y de asignación externa'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d9ea37f5-0a9e-4401-8fc3-1e6fd44c49f9
caps.latest.revision: 2
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 4d3fc297078c9f6c1ac8b2d8a498050f294a5437
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-validate-dbml-and-external-mapping-files"></a>Cómo: Validar archivos DBML y de asignación externa
Los archivos de asignación externa y los archivos .dbml que se modifican se deben validar con sus respectivas definiciones de esquema. Este tema proporciona a los usuarios de Visual Studio con los pasos para implementar el proceso de validación.  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
### <a name="to-validate-a-dbml-or-xml-file"></a>Para validar un archivo .dbml o XML  
  
1.  En Visual Studio **archivo** menú, elija **abiertos**y, a continuación, haga clic en **archivo**.  
  
2.  En el **archivos abiertos** diálogo cuadro, haga clic en el archivo .dbml o XML asignación que desea validar.  
  
     El archivo se abre en el **Editor XML**.  
  
3.  Haga clic en la ventana y, a continuación, haga clic en **propiedades**.  
  
4.  En el **propiedades** ventana, haga clic en el botón de puntos suspensivos para la **esquemas** propiedad.  
  
     El **esquemas XML** abre el cuadro de diálogo.  
  
5.  Observe cuál es la definición de esquema adecuada para lo que desea.  
  
    -   DbmlSchema.xsd es la definición de esquema para validar un archivo .dbml. Para obtener más información, consulte [generación de código en LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).  
  
    -   LinqToSqlMapping.xsd es la definición de esquema para validar un archivo XML de asignación externa. Para obtener más información, consulte [asignación externa](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).  
  
6.  En el **Use** columna de la fila de la definición de esquema que desee, haga clic para abrir el cuadro de lista desplegable y, a continuación, haga clic en **utilizar este esquema**.  
  
     El archivo de definición de esquema está asociado ahora con su archivo de asignación DBML o XML.  
  
     Asegúrese de que no hay otras definiciones de esquema seleccionadas.  
  
7.  En el **vista** menú, haga clic en **lista de errores**.  
  
     Determine si se han generado errores, advertencias o mensajes. Si no, el archivo XML es válido respecto a la definición de esquema.  
  
## <a name="alternate-method-for-supplying-schema-definition"></a>Método alternativo para proporcionar la definición de esquema  
 Si por alguna razón el .xsd adecuado archivo no aparece en la **esquemas XML** cuadro de diálogo, puede descargar el archivo .xsd de un tema de ayuda. Los pasos siguientes le ayudarán a guardar el archivo descargado en el formato de Unicode requerido por el Editor XML de Visual Studio.  
  
#### <a name="to-copy-a-schema-definition-file-from-a-help-topic"></a>Para copiar un archivo de definición de esquema de un tema de Ayuda  
  
1.  Busque el tema de Ayuda que contiene la definición de esquema tal como se ha descrito anteriormente en este tema.  
  
    -   Para los archivos .dbml, consulte [generación de código en LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).  
  
    -   Para los archivos de asignación externo, vea [asignación externa](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).  
  
2.  Haga clic en **copiar código** para copiar el archivo de código en el Portapapeles.  
  
3.  Inicie Bloc de notas para crear un nuevo archivo.  
  
4.  Pegue el código del Portapapeles en el archivo del Bloc de notas.  
  
5.  En el Bloc de notas **archivo** menú, haga clic en **Guardar como**.  
  
6.  En el **codificación** cuadro, seleccione **Unicode**.  
  
    > [!IMPORTANT]
    >  Esta selección garantiza que el marcador de orden de bytes Unicode-16 (`FFFE`) se antepone al archivo de texto.  
  
7.  En el **nombre de archivo** cuadro, cree un nombre de archivo con una extensión .xsd.  
  
## <a name="see-also"></a>Vea también  
 [Referencia](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
