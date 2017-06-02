---
title: "C&#243;mo: Validar archivos de asignaci&#243;n externa y DBML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d9ea37f5-0a9e-4401-8fc3-1e6fd44c49f9
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# C&#243;mo: Validar archivos de asignaci&#243;n externa y DBML
Los archivos de asignación externa y los archivos .dbml que se modifican se deben validar con sus respectivas definiciones de esquema.  En este tema se proporciona a los usuarios de [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] los pasos necesarios para implementar el proceso de validación.  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
### Para validar un archivo .dbml o XML  
  
1.  En el menú **Archivo** de Visual Studio, elija **Abrir** y, a continuación, haga clic en **Archivo**.  
  
2.  En el cuadro de diálogo **Abrir archivo**, haga clic en el archivo de asignación .dbml o XML que desea validar.  
  
     El archivo se abre en el **Editor XML**.  
  
3.  Haga clic con el botón secundario del mouse en la ventana y, a continuación, haga clic en **Propiedades**.  
  
4.  En la ventana **Propiedades**, haga clic en el botón de puntos suspensivos \(…\) en la propiedad **Esquemas**.  
  
     Se abrirá el cuadro de diálogo **Esquemas XML**.  
  
5.  Observe cuál es la definición de esquema adecuada para lo que desea.  
  
    -   DbmlSchema.xsd es la definición de esquema para validar un archivo .dbml.  Para obtener más información, consulta [Generación de código en LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).  
  
    -   LinqToSqlMapping.xsd es la definición de esquema para validar un archivo XML de asignación externa.  Para obtener más información, consulta [Asignación externa](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).  
  
6.  En la columna **Uso** de la fila de definición de esquema que desee, haga clic para abrir el cuadro desplegable y, a continuación, haga clic en **Usar este esquema**.  
  
     El archivo de definición de esquema está asociado ahora con su archivo de asignación DBML o XML.  
  
     Asegúrese de que no hay otras definiciones de esquema seleccionadas.  
  
7.  En el menú **Ver**, haga clic en **Lista de errores**.  
  
     Determine si se han generado errores, advertencias o mensajes.  Si no, el archivo XML es válido respecto a la definición de esquema.  
  
## Método alternativo para proporcionar la definición de esquema  
 Si por alguna razón el archivo .xsd adecuado no aparece en el cuadro de diálogo **Esquemas XML**, puede descargarlo de un tema de Ayuda.  Los pasos siguientes le indicarán cómo guardar el archivo descargado en el formato Unicode que requiere el Editor XML de [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)].  
  
#### Para copiar un archivo de definición de esquema de un tema de Ayuda  
  
1.  Busque el tema de Ayuda que contiene la definición de esquema tal como se ha descrito anteriormente en este tema.  
  
    -   En el caso de los archivos .dbml, vea [Generación de código en LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).  
  
    -   En el caso de los archivos de asignación externa, vea [Asignación externa](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).  
  
2.  Haga clic en **Copiar código en el Portapapeles** para copiar el archivo de código en el Portapapeles.  
  
3.  Inicie Bloc de notas para crear un nuevo archivo.  
  
4.  Pegue el código del Portapapeles en el archivo del Bloc de notas.  
  
5.  En el menú **Archivo** del Bloc de notas, haga clic en **Guardar como**.  
  
6.  En el cuadro **Codificación**, seleccione **Unicode**.  
  
    > [!IMPORTANT]
    >  Esta selección garantiza que el marcador de orden de bytes Unicode\-16 \(`FFFE`\) se antepone al archivo de texto.  
  
7.  En el cuadro **Nombre de archivo**, cree un nombre de archivo con extensión .xsd.  
  
## Vea también  
 [Referencia](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)