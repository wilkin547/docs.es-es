---
title: Pasos habituales para usar LINQ to SQL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a88bd51-bd74-48f7-a9b1-f650e8d55a3e
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 5115fce1d5060d258ae5feeefd99aaaf5123a123
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="typical-steps-for-using-linq-to-sql"></a>Pasos habituales para usar LINQ to SQL
Para implementar una aplicación [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], debe seguir los pasos que se describen más adelante en este tema. Observe que muchos pasos son opcionales. Es muy posible que pueda utilizar su modelo de objetos en su estado predeterminado.  
  
 Para agilizar el proceso, utilice el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para crear su modelo de objetos y poder empezar a codificar sus consultas.  
  
## <a name="creating-the-object-model"></a>Crear el modelo de objetos  
 El primer paso es crear un modelo de objetos a partir de los metadatos de una base de datos relacional existente. El modelo de objetos representa la base de datos según el lenguaje de programación del desarrollador. Para obtener más información, consulte [el modelo de LINQ to SQL objeto](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).  
  
### <a name="1-select-a-tool-to-create-the-model"></a>1. Seleccionar una herramienta para crear el modelo  
 Tres herramientas están disponibles para crear el modelo.  
  
-   El [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]  
  
     Este diseñador proporciona una interfaz de usuario completa para crear un modelo de objetos a partir de una base de datos existente. Esta herramienta forma parte del IDE de [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] y es perfecta para bases de datos medianas o pequeñas.  
  
-   Herramienta de generación de código SQLMetal  
  
     Esta herramienta de línea de comandos proporciona un conjunto de opciones ligeramente diferentes de las del [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]. Las bases de datos grandes se modelan mejor con esta herramienta. Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
-   Editor de código  
  
     Puede escribir su propio código utilizando el editor de código de [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] u otro editor. No recomendamos este enfoque, que puede ser susceptible a errores, cuando se tiene una base de datos existente y se puede utilizar el [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] o la herramienta SQLMetal. Sin embargo, el editor de código puede ser muy útil para perfeccionar o modificar el código ya generado con otras herramientas. Para obtener más información, consulte [Cómo: personalizar clases de entidad mediante el Editor de código](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md).  
  
### <a name="2-select-the-kind-of-code-you-want-to-generate"></a>2. Seleccionar el tipo de código que se desea generar  
  
-   Un archivo de código fuente de C# o [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] para la asignación basada en atributos.  
  
     Después, incluirá este archivo de código en su proyecto de [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]. Para obtener más información, consulte [asignación basada en el atributo](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
-   Un archivo XML para la asignación externa.  
  
     Con este enfoque puede mantener los metadatos de la asignación fuera del código de aplicación. Para obtener más información, consulte [asignación externa](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).  
  
    > [!NOTE]
    >  El [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] no admite la generación de archivos de asignación externos. Debe utilizar la herramienta SQLMetal para implementar esta característica.  
  
-   Un archivo DBML, que se puede modificar antes de generar el archivo de código definitivo.  
  
     Ésta es una característica avanzada.  
  
### <a name="3-refine-the-code-file-to-reflect-the-needs-of-your-application"></a>3. Perfeccionar el archivo de código para reflejar las necesidades de una aplicación  
 Para este propósito, puede utilizar el [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] o el editor de código.  
  
## <a name="using-the-object-model"></a>Usar el modelo de objetos  
 La ilustración siguiente muestra la relación entre el programador y los datos en un escenario de dos niveles. Para otros escenarios, consulte [de N niveles y las aplicaciones remotas con LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md).  
  
 ![DLinqObjectModel](../../../../../../docs/framework/data/adonet/sql/linq/media/dlinqobjectmodel.png "DLinqObjectModel")  
  
 Ahora que tiene un modelo de objetos, debe describir las solicitudes de información y manipular los datos dentro de ese modelo. Debe pensar en términos de los objetos y las propiedades del modelo de objetos, y no en términos de las filas y columnas de la base de datos. No tratará directamente con la base de datos.  
  
 Al indicar a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] que ejecute una consulta que ha descrito o llamada `SubmitChanges()` en los datos que han manipulado, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] se comunica con la base de datos en el idioma de la base de datos.  
  
 A continuación, se presentan los pasos típicos para utilizar el modelo de objetos creado.  
  
### <a name="1-create-queries-to-retrieve-information-from-the-database"></a>1. Crear consultas para recuperar información de la base de datos  
 Para obtener más información, consulte [conceptos sobre consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md) y [ejemplos de consultas](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md).  
  
### <a name="2-override-default-behaviors-for-insert-update-and-delete"></a>2. Invalidar los comportamientos predeterminados de Insert, Update y Delete  
 Este paso es opcional. Para obtener más información, consulte [personalizar operaciones de inserción, actualización y eliminar](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
  
### <a name="3-set-appropriate-options-to-detect-and-report-concurrency-conflicts"></a>3. Establecer las opciones adecuadas para detectar y notificar conflictos de simultaneidad  
 Puede mantener la configuración de administración de conflictos de simultaneidad predeterminada del modelo o puede cambiarla para ajustarla sus fines concretos. Para obtener más información, consulte [Cómo: especificar que los miembros se comprueba si hay conflictos de simultaneidad](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md) y [Cómo: especificar si las excepciones de simultaneidad se producen](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-when-concurrency-exceptions-are-thrown.md).  
  
### <a name="4-establish-an-inheritance-hierarchy"></a>4. Establecer una jerarquía de herencia  
 Este paso es opcional. Para obtener más información, consulte [compatibilidad de herencia](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md).  
  
### <a name="5-provide-an-appropriate-user-interface"></a>5. Proporcionar una interfaz de usuario adecuada  
 Este paso es opcional y depende de cómo se vaya a utilizar la aplicación.  
  
### <a name="6-debug-and-test-your-application"></a>6. Depurar y probar la aplicación  
 Para obtener más información, consulte [capacidad de depuración](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md).  
  
## <a name="see-also"></a>Vea también  
 [Introducción](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)  
 [Crear el modelo de objetos](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 [Procedimientos almacenados](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
