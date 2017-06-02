---
title: "Aprender mediante tutoriales | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a8ae2965-6a49-4155-89b0-7fab2c488ab1
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Aprender mediante tutoriales
La documentación de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proporciona varios tutoriales.  En este tema se resuelven algunos de los problemas generales que plantean los tutoriales y se proporcionan vínculos a varios tutoriales de iniciación a través de los cuales conocerá [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
> [!NOTE]
>  En los tutoriales de esta sección introductoria, conocerá el código básico que admite la tecnología [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  En la práctica real, normalmente utilizará el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] y proyectos de Windows Forms para implementar sus aplicaciones [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  La documentación de [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] proporciona ejemplos y tutoriales con esta finalidad.  
  
## Tutoriales introductorios  
 En esta sección hay varios tutoriales disponibles.  En estos tutoriales se utiliza la base de datos de ejemplo Northwind y en ellos se presentan las características de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] paso a paso, con el mínimo grado de dificultad.  
  
 Normalmente, se avanza de la siguiente manera:  
  
|Objetivo|Visual Basic|C\#|  
|--------------|------------------|---------|  
|Crear una clase de entidad y ejecutar una consulta simple.|[Tutorial: Modelo de objetos simple y consultas \(Visual Basic\)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-simple-object-model-and-query-visual-basic.md)|[Tutorial: Modelo de objetos simple y consultas \(C\#\)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-simple-object-model-and-query-csharp.md)|  
|Agregar una segunda clase y ejecutar una consulta más compleja.<br /><br /> \(Requiere haber completado el tutorial anterior\).|[Tutorial: Realizar consultas en varias relaciones \(Visual Basic\)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-visual-basic.md)|[Tutorial: Realizar consultas en varias relaciones \(C\#\)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-csharp.md)|  
|Agregar, cambiar y eliminar elementos en la base de datos.|[Tutorial: Manipular datos \(Visual Basic\)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-manipulating-data-visual-basic.md)|[Tutorial: Manipular datos \(C\#\)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-manipulating-data-csharp.md)|  
|Utilizar procedimientos almacenados.|[Tutorial: Usar solo procedimientos almacenados \(Visual Basic\)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-visual-basic.md)|[Tutorial: Usar solo procedimientos almacenados \(C\#\)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-csharp.md)|  
  
## General  
 La información siguiente corresponde a estos tutoriales en general:  
  
-   Entorno: cada tutorial [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] utiliza [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] como entorno de desarrollo integrado \(IDE\).  
  
-   Motores de SQL: estos tutoriales se han escrito para ser implementados con SQL Server Express.  Si no tiene SQL Server Express, puede descargarlo gratuitamente.  Para obtener más información, consulte [Descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
    > [!NOTE]
    >  Los tutoriales de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] utilizan un nombre de archivo como cadena de conexión.  La simple especificación de un nombre de archivo es una ventaja que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ofrece para los usuarios de SQL Server Express.  Siempre preste atención a los problemas de seguridad.  Para obtener más información, consulte [Seguridad en LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/security-in-linq-to-sql.md).  
  
-   Normalmente, los tutoriales de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] requieren la base de datos de ejemplo Northwind.  Para obtener más información, consulte [Descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
-   Los cuadros de diálogo y comandos de menú que se ven en los tutoriales pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición de [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] activos.  Para cambiar la configuración, haga clic en **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, consulte [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
-   Para los tutoriales que se ocupan de escenarios de varios niveles, debe disponer de un servidor en un equipo distinto del equipo de desarrollo, y debe tener los permisos de acceso adecuados para el servidor.  
  
-   El nombre de la clase que normalmente representa la tabla Orders en la base de datos de ejemplo Northwind es `[Order]`.  Los caracteres de escape son necesarios, ya que `Order` es una palabra clave en [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)].  
  
## Solución de problemas  
 Pueden producirse errores en tiempo de ejecución, ya que no dispone de los permisos suficientes para tener acceso a las bases de datos utilizadas en estos tutoriales.  Los pasos siguientes pueden ayudarle a resolver los problemas más comunes.  
  
### Problemas de inicio de sesión  
 Su aplicación podría estar intentando tener acceso a la base de datos con un inicio de sesión de base de datos no admitido.  
  
##### Para comprobar o cambiar el inicio de sesión de base de datos  
  
1.  En el menú **Inicio** de Windows, elija **Todos los programas**, **Microsoft SQL Server 2005**, **Herramientas de configuración** y, a continuación, haga clic en **Administrador de configuración de SQL Server**.  
  
2.  En el panel izquierdo del **Administrador de configuración de SQL Server**, haga clic en **Servicios de SQL Server 2005**.  
  
3.  En el panel derecho, haga clic con el botón secundario en **SQL Server \(SQLEXPRESS\)** y, a continuación, haga clic en **Propiedades**.  
  
4.  Haga clic en la pestaña **Iniciar sesión** y compruebe de qué manera se intenta iniciar sesión en el servidor.  
  
     En la mayoría de los casos, funciona **Sistema local**.  
  
     Si realiza alguna modificación, haga clic en **Reiniciar** para reiniciar el servicio.  
  
### Protocolos  
 A veces, los protocolos podrían no estar establecidos correctamente para el acceso de la aplicación a la base de datos.  Por ejemplo, el protocolo **Canalizaciones con nombre**, que es necesario para los tutoriales de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], no está habilitado de forma predeterminada.  
  
##### Para habilitar el protocolo Canalizaciones con nombre  
  
1.  En el panel izquierdo del **Administrador de configuración de SQL Server**, expanda **Configuración de red de SQL Server 2005** y, a continuación, haga clic en **Protocolos de SQLEXPRESS**.  
  
2.  En el panel derecho, compruebe que el protocolo **Canalizaciones con nombre** está habilitado.  Si no lo está, haga clic con el botón secundario en **Canalizaciones con nombre** y, a continuación, haga clic en **Habilitar**.  
  
     Tendrá que detener y reiniciar el servicio.  Siga los pasos de la sección siguiente.  
  
### Detener y reiniciar el servicio  
 Para que los cambios surtan efecto, es necesario detener y reiniciar los servicios.  
  
##### Para detener y reiniciar el servicio  
  
1.  En el panel izquierdo del **Administrador de configuración de SQL Server**, haga clic en **Servicios de SQL Server 2005**.  
  
2.  En el panel derecho, haga clic con el botón secundario en **SQL Server \(SQLEXPRESS\)** y, a continuación, haga clic en **Detener**.  
  
3.  Haga clic con el botón secundario en **SQL Server \(SQLEXPRESS\)** y, a continuación, haga clic en **Reiniciar**.  
  
## Vea también  
 [Introducción](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)