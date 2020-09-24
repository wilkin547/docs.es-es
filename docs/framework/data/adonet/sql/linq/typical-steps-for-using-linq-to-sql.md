---
title: Pasos habituales para usar LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 9a88bd51-bd74-48f7-a9b1-f650e8d55a3e
ms.openlocfilehash: dc8c4be1e895ee5c4c7947e6311e5bf71008490f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164265"
---
# <a name="typical-steps-for-using-linq-to-sql"></a>Pasos habituales para usar LINQ to SQL

Para implementar una aplicación [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], debe seguir los pasos que se describen más adelante en este tema. Observe que muchos pasos son opcionales. Es muy posible que pueda utilizar su modelo de objetos en su estado predeterminado.  
  
 Para un inicio muy rápido, use el Object Relational Designer para crear el modelo de objetos y comenzar a codificar las consultas.  
  
## <a name="creating-the-object-model"></a>Crear el modelo de objetos  

 El primer paso es crear un modelo de objetos a partir de los metadatos de una base de datos relacional existente. El modelo de objetos representa la base de datos según el lenguaje de programación del desarrollador. Para obtener más información, vea [el LINQ to SQL modelo de objetos](the-linq-to-sql-object-model.md).  
  
### <a name="1-select-a-tool-to-create-the-model"></a>1. Seleccione una herramienta para crear el modelo.  

 Tres herramientas están disponibles para crear el modelo.  
  
- El Object Relational Designer  
  
     Este diseñador proporciona una interfaz de usuario completa para crear un modelo de objetos a partir de una base de datos existente. Esta herramienta forma parte del IDE de Visual Studio y se adapta mejor a las bases de datos pequeñas o medianas.  
  
- Herramienta de generación de código SQLMetal  
  
     Esta utilidad de línea de comandos proporciona un conjunto de opciones ligeramente diferente de Object Relational Designer. Las bases de datos grandes se modelan mejor con esta herramienta. Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
- Editor de código  
  
     Puede escribir su propio código mediante el editor de código de Visual Studio o cualquier otro editor. No se recomienda este enfoque, que puede ser propenso a errores, si tiene una base de datos existente y puede usar Object Relational Designer o la herramienta SQLMetal. Sin embargo, el editor de código puede ser muy útil para perfeccionar o modificar el código ya generado con otras herramientas. Para obtener más información, vea [Cómo: personalizar clases de entidad mediante el editor de código](how-to-customize-entity-classes-by-using-the-code-editor.md).  
  
### <a name="2-select-the-kind-of-code-you-want-to-generate"></a>2. Seleccione el tipo de código que desea generar.  
  
- Un archivo de código fuente de C# o Visual Basic para la asignación basada en atributos.  
  
     Después, incluya este archivo de código en el proyecto de Visual Studio. Para obtener más información, consulte [asignación basada en atributos](attribute-based-mapping.md).  
  
- Un archivo XML para la asignación externa.  
  
     Con este enfoque puede mantener los metadatos de la asignación fuera del código de aplicación. Para obtener más información, consulte [asignación externa](external-mapping.md).  
  
    > [!NOTE]
    > Object Relational Designer no admite la generación de archivos de asignación externos. Debe utilizar la herramienta SQLMetal para implementar esta característica.  
  
- Un archivo DBML, que se puede modificar antes de generar el archivo de código definitivo.  
  
     Ésta es una característica avanzada.  
  
### <a name="3-refine-the-code-file-to-reflect-the-needs-of-your-application"></a>3. Refine el archivo de código para reflejar las necesidades de la aplicación.  

 Para este propósito, puede utilizar el Object Relational Designer o el editor de código.  
  
## <a name="using-the-object-model"></a>Usar el modelo de objetos  

 La ilustración siguiente muestra la relación entre el programador y los datos en un escenario de dos niveles. Para otros escenarios, consulte [aplicaciones de N niveles y remotas con LINQ to SQL](n-tier-and-remote-applications-with-linq-to-sql.md).  
  
 ![Captura de pantalla que muestra el modelo de objetos de Linq.](./media/the-linq-to-sql-object-model/linq-object-model-two-tier.png)  
  
 Ahora que tiene un modelo de objetos, debe describir las solicitudes de información y manipular los datos dentro de ese modelo. Debe pensar en términos de los objetos y las propiedades del modelo de objetos, y no en términos de las filas y columnas de la base de datos. No tratará directamente con la base de datos.  
  
 Al indicar [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] a que ejecute una consulta que ha descrito o que llame a `SubmitChanges()` en los datos que ha manipulado, se [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] comunica con la base de datos en el idioma de la base de datos.  
  
 A continuación, se presentan los pasos típicos para utilizar el modelo de objetos creado.  
  
### <a name="1-create-queries-to-retrieve-information-from-the-database"></a>1. cree consultas para recuperar información de la base de datos.  

 Para obtener más información, vea [conceptos de consultas](query-concepts.md) y ejemplos de [consultas](query-examples.md).  
  
### <a name="2-override-default-behaviors-for-insert-update-and-delete"></a>2. invalidar los comportamientos predeterminados para INSERT, Update y DELETE.  

 Este paso es opcional. Para obtener más información, vea [personalizar las operaciones de inserción, actualización y eliminación](customizing-insert-update-and-delete-operations.md).  
  
### <a name="3-set-appropriate-options-to-detect-and-report-concurrency-conflicts"></a>3. establezca las opciones adecuadas para detectar y notificar conflictos de simultaneidad.  

 Puede mantener la configuración de administración de conflictos de simultaneidad predeterminada del modelo o puede cambiarla para ajustarla sus fines concretos. Para obtener más información, vea [Cómo: especificar en qué miembros se comprueban los conflictos de simultaneidad](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md) y [Cómo: especificar Cuándo se inician las excepciones de simultaneidad](how-to-specify-when-concurrency-exceptions-are-thrown.md).  
  
### <a name="4-establish-an-inheritance-hierarchy"></a>4. establezca una jerarquía de herencia.  

 Este paso es opcional. Para obtener más información, consulte [compatibilidad con la herencia](inheritance-support.md).  
  
### <a name="5-provide-an-appropriate-user-interface"></a>5. proporcione una interfaz de usuario adecuada.  

 Este paso es opcional y depende de cómo se vaya a utilizar la aplicación.  
  
### <a name="6-debug-and-test-your-application"></a>6. depurar y probar la aplicación.  

 Para obtener más información, consulte [compatibilidad con la depuración](debugging-support.md).  
  
## <a name="see-also"></a>Consulte también

- [Introducción](getting-started.md)
- [Crear el modelo de objetos](creating-the-object-model.md)
- [Procedimientos almacenados](stored-procedures.md)
