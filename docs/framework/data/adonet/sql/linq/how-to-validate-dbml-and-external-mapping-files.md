---
description: 'Más información acerca de cómo: validar archivos DBML y de asignación externa'
title: Procedimiento para validar archivos DBML y de asignación externa
ms.date: 03/30/2017
ms.assetid: d9ea37f5-0a9e-4401-8fc3-1e6fd44c49f9
ms.openlocfilehash: 46e5c787bef8e152020fc97631ef8c1c4928fe74
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785788"
---
# <a name="how-to-validate-dbml-and-external-mapping-files"></a>Procedimiento para validar archivos DBML y de asignación externa

Los archivos de asignación externa y los archivos .dbml que se modifican se deben validar con sus respectivas definiciones de esquema. En este tema se proporciona a los usuarios de Visual Studio los pasos necesarios para implementar el proceso de validación.

[!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]

### <a name="to-validate-a-dbml-or-xml-file"></a>Para validar un archivo .dbml o XML

1. En el menú **archivo** de Visual Studio, elija **abrir** y, a continuación, haga clic en **archivo**.

2. En el cuadro de diálogo **Abrir archivo** , haga clic en el archivo de asignación. DBML o XML que desea validar.

    El archivo se abre en el **Editor XML**.

3. Haga clic con el botón secundario en la ventana y, a continuación, haga clic en **propiedades**.

4. En la ventana **propiedades** , haga clic en los puntos suspensivos de la propiedad **schemas** .

    Se abrirá el cuadro de diálogo **esquemas XML** .

5. Observe cuál es la definición de esquema adecuada para lo que desea.

    - DbmlSchema.xsd es la definición de esquema para validar un archivo .dbml. Para obtener más información, vea [generación de código en LINQ to SQL](code-generation-in-linq-to-sql.md).

    - LinqToSqlMapping.xsd es la definición de esquema para validar un archivo XML de asignación externa. Para obtener más información, consulte [asignación externa](external-mapping.md).

6. En la columna **usar** de la fila definición de esquema deseada, haga clic para abrir el cuadro desplegable y, a continuación, haga clic en **usar este esquema**.

    El archivo de definición de esquema está asociado ahora con su archivo de asignación DBML o XML.

    Asegúrese de que no hay otras definiciones de esquema seleccionadas.

7. En el menú **Ver** , haga clic en **Lista de errores**.

    Determine si se han generado errores, advertencias o mensajes. Si no, el archivo XML es válido respecto a la definición de esquema.

## <a name="alternate-method-for-supplying-schema-definition"></a>Método alternativo para proporcionar la definición de esquema

Si, por alguna razón, el archivo. xsd correspondiente no aparece en el cuadro de diálogo **esquemas XML** , puede descargar el archivo. xsd de un tema de ayuda. Los siguientes pasos le ayudarán a guardar el archivo descargado en el formato Unicode requerido por el editor XML de Visual Studio.

#### <a name="to-copy-a-schema-definition-file-from-a-help-topic"></a>Para copiar un archivo de definición de esquema de un tema de Ayuda

1. Busque el tema de Ayuda que contiene la definición de esquema tal como se ha descrito anteriormente en este tema.

    - Para los archivos. dbml, vea [generación de código en LINQ to SQL](code-generation-in-linq-to-sql.md).

    - Para los archivos de asignación externa, consulte [asignación externa](external-mapping.md).

2. Haga clic en **Copiar código** para copiar el archivo de código en el portapapeles.

3. Inicie Bloc de notas para crear un nuevo archivo.

4. Pegue el código del Portapapeles en el archivo del Bloc de notas.

5. En el menú **archivo** del Bloc de notas, haga clic en **Guardar como**.

6. En el cuadro **codificación** , seleccione **Unicode**.

    > [!IMPORTANT]
    > Esta selección garantiza que el marcador de orden de bytes Unicode-16 (`FFFE`) se antepone al archivo de texto.

7. En el cuadro **nombre de archivo** , cree un nombre de archivo con la extensión. xsd.

## <a name="see-also"></a>Vea también

- [Referencia](reference.md)
