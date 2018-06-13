---
title: Aprender con tutoriales
ms.date: 03/30/2017
ms.assetid: a8ae2965-6a49-4155-89b0-7fab2c488ab1
ms.openlocfilehash: 028bd2af9ba88136e5955c6776b0d765af20fca3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33362226"
---
# <a name="learning-by-walkthroughs"></a>Aprender con tutoriales
El [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentación proporciona varios tutoriales. En este tema se resuelven algunos de los problemas generales que plantean los tutoriales y se proporcionan vínculos a varios tutoriales de iniciación a través de los cuales conocerá [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
> [!NOTE]
>  En los tutoriales de esta sección introductoria, conocerá el código básico que admite la tecnología [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. En la práctica real, normalmente utilizará el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] y proyectos de Windows Forms para implementar sus aplicaciones [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. La documentación de [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] proporciona ejemplos y tutoriales con esta finalidad.  
  
## <a name="getting-started-walkthroughs"></a>Tutoriales introductorios  
 En esta sección hay varios tutoriales disponibles. En estos tutoriales se utiliza la base de datos de ejemplo Northwind y en ellos se presentan las características de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] paso a paso, con el mínimo grado de dificultad.  
  
 Normalmente, se avanza de la siguiente manera:  
  
|Objetivo|Visual Basic|C#|  
|---------------|------------------|---------|  
|Crear una clase de entidad y ejecutar una consulta simple.|[Tutorial: Modelo de objetos simple y consultas (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-simple-object-model-and-query-visual-basic.md)|[Tutorial: Modelo de objetos simple y consultas (C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-simple-object-model-and-query-csharp.md)|  
|Agregar una segunda clase y ejecutar una consulta más compleja.<br /><br /> (Requiere haber completado el tutorial anterior).|[Tutorial: Realizar consultas en varias relaciones (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-visual-basic.md)|[Tutorial: Realizar consultas en varias relaciones (C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-csharp.md)|  
|Agregar, cambiar y eliminar elementos en la base de datos.|[Tutorial: Manipular datos (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-manipulating-data-visual-basic.md)|[Tutorial: Manipular datos (C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-manipulating-data-csharp.md)|  
|Utilizar procedimientos almacenados.|[Tutorial: Usar solo procedimientos almacenados (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-visual-basic.md)|[Tutorial: Usar solo procedimientos almacenados (C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-csharp.md)|  
  
## <a name="general"></a>General  
 La información siguiente corresponde a estos tutoriales en general:  
  
-   Entorno: Cada [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tutorial utiliza Visual Studio como entorno de desarrollo integrado (IDE).  
  
-   Motores de SQL: estos tutoriales se han escrito para ser implementados con SQL Server Express. Si no tiene SQL Server Express, puede descargarlo gratuitamente. Para obtener más información, consulte [descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
    > [!NOTE]
    >  Los tutoriales de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] utilizan un nombre de archivo como cadena de conexión. La simple especificación de un nombre de archivo es una ventaja que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ofrece para los usuarios de SQL Server Express. Siempre preste atención a los problemas de seguridad. Para obtener más información, consulte [seguridad en LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/security-in-linq-to-sql.md).  
  
-   [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tutoriales normalmente requieren la base de datos de ejemplo Northwind. Para obtener más información, consulte [descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
-   Los cuadros de diálogo y comandos de menú que se ven en los tutoriales pueden diferir de los descritos en la Ayuda, dependiendo de la edición de Visual Studio o configuración activa. Para cambiar la configuración, haga clic en **Importar y exportar configuraciones** en el menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
-   Para los tutoriales que se ocupan de escenarios de varios niveles, debe disponer de un servidor en un equipo distinto del equipo de desarrollo, y debe tener los permisos de acceso adecuados para el servidor.  
  
-   El nombre de la clase que normalmente representa la tabla Orders en la base de datos de ejemplo Northwind es `[Order]`. Las secuencias de escape son necesario porque `Order` es una palabra clave en Visual Basic.  
  
## <a name="troubleshooting"></a>Solución de problemas  
 Pueden producirse errores en tiempo de ejecución, ya que no dispone de los permisos suficientes para tener acceso a las bases de datos utilizadas en estos tutoriales. Los pasos siguientes pueden ayudarle a resolver los problemas más comunes.  
  
### <a name="log-on-issues"></a>Problemas de inicio de sesión  
 Su aplicación podría estar intentando tener acceso a la base de datos con un inicio de sesión de base de datos no admitido.  
  
##### <a name="to-verify-or-change-the-database-log-on"></a>Para comprobar o cambiar el inicio de sesión de base de datos  
  
1.  En las ventanas **iniciar** menú, elija **todos los programas**, **Microsoft SQL Server 2005**, seleccione **herramientas de configuración**y, a continuación, haga clic en **Administrador de configuración de SQL Server**.  
  
2.  En el panel izquierdo de la **Administrador de configuración de SQL Server**, haga clic en **servicios de SQL Server 2005**.  
  
3.  En el panel derecho, haga clic en **SQL Server (SQLEXPRESS)** y, a continuación, haga clic en **propiedades**.  
  
4.  Haga clic en el **Log On** ficha y compruebe cómo se está intentando iniciar sesión en el servidor.  
  
     En la mayoría de los casos, **sistema Local** funciona.  
  
     Si realiza un cambio, haga clic en **reiniciar** para reiniciar el servicio.  
  
### <a name="protocols"></a>Protocolos  
 A veces, los protocolos podrían no estar establecidos correctamente para el acceso de la aplicación a la base de datos. Por ejemplo, el **canalizaciones con nombre** protocolo, que es necesario para los tutoriales en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], no está habilitado de forma predeterminada.  
  
##### <a name="to-enable-the-named-pipes-protocol"></a>Para habilitar el protocolo Canalizaciones con nombre  
  
1.  En el panel izquierdo de la **Administrador de configuración de SQL Server**, expanda **configuración de red de SQL Server 2005**y, a continuación, haga clic en **protocolos de SQLEXPRESS**.  
  
2.  En el panel derecho, compruebe que la **canalizaciones con nombre** protocolo está habilitado. Si no es así, haga clic en **canalizaciones con nombre** y, a continuación, haga clic en **habilitar**.  
  
     Tendrá que detener y reiniciar el servicio. Siga los pasos de la sección siguiente.  
  
### <a name="stopping-and-restarting-the-service"></a>Detener y reiniciar el servicio  
 Para que los cambios surtan efecto, es necesario detener y reiniciar los servicios.  
  
##### <a name="to-stop-and-restart-the-service"></a>Para detener y reiniciar el servicio  
  
1.  En el panel izquierdo de la **Administrador de configuración de SQL Server**, haga clic en **servicios de SQL Server 2005**.  
  
2.  En el panel derecho, haga clic en **SQL Server (SQLEXPRESS)** y, a continuación, haga clic en **detener**.  
  
3.  Haga clic en **SQL Server (SQLEXPRESS)** y, a continuación, haga clic en **reiniciar**.  
  
## <a name="see-also"></a>Vea también  
 [Introducción](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
