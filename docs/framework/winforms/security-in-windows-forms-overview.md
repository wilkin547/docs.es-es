---
title: Información general sobre la seguridad en formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- code access security [Windows Forms], Windows Forms
- permissions [Windows Forms], Windows Forms
- Windows Forms, security
- security [Windows Forms], about security
- access control [Windows Forms], Windows Forms
ms.assetid: 4810dc9f-ea23-4ce1-8ea1-657f0ff1d820
ms.openlocfilehash: 54fc56e5e7d6ee5cd0e7bc55bd22c7d4127eb4d3
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43532123"
---
# <a name="security-in-windows-forms-overview"></a>Información general sobre la seguridad en formularios Windows Forms
Antes del lanzamiento de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], todo el código que se ejecutaba en el equipo de un usuario tenía los mismos derechos o permisos de acceso a los recursos que los que tenía un usuario del equipo. Por ejemplo, si el usuario tenía acceso al sistema de archivos, el código también tenía acceso al sistema de archivos; si el usuario tenía acceso a una base de datos, el código también tenía acceso a esa base de datos. Aunque estos derechos o permisos pueden ser aceptables para el código de los ejecutables que el usuario ha instalado explícitamente en el equipo local, no pueden ser aceptables para el código potencialmente malintencionado procedente de Internet o de una intranet local. Este código no debe tener acceso a los recursos del equipo del usuario sin permiso.  
  
 El [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] presenta una infraestructura denominada seguridad de acceso del código que permite diferenciar los permisos o derechos que tiene el código de los que tiene el usuario. De forma predeterminada, el código procedente de Internet y de la intranet solo se puede ejecutar en lo que se conoce como confianza parcial. La confianza parcial somete una aplicación a una serie de restricciones: entre otras cosas, la aplicación tiene restringido el acceso al disco duro local y no puede ejecutar código no administrado. [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] controla los recursos para los que el código tiene permiso de acceso en función de la identidad de ese código: de dónde procede, si tiene [ensamblados con nombre seguro](../../../docs/framework/app-domains/strong-named-assemblies.md), si está firmado con un certificado, etc.  
  
 La tecnología de [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)], que se usa para implementar aplicaciones de Windows Forms, facilita el desarrollo de aplicaciones que se ejecutan en confianza parcial, en plena confianza o en confianza parcial con permisos elevados. [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] proporciona características como la elevación de permisos y la implementación de aplicaciones de confianza para que la aplicación pueda solicitar la plena confianza o permisos elevados del usuario local de manera responsable.  
  
## <a name="understanding-security-in-the-net-framework"></a>Descripción de la seguridad en .NET Framework  
 La seguridad de acceso del código proporciona al código varios grados de confianza que dependen de su procedencia y de otros aspectos de la identidad del código. Para obtener más información sobre la evidencia que Common Language Runtime usa para determinar la directiva de seguridad, consulte el artículo sobre [evidencia](https://msdn.microsoft.com/library/64ceb7c8-a0b4-46c4-97dc-6c22da0539da). La seguridad de acceso del código ayuda a proteger los sistemas informáticos frente a código malintencionado y también evita que el código de confianza comprometa la seguridad de manera intencionada o accidental. Asimismo, le ofrece más control sobre las acciones que puede llevar a cabo la aplicación, ya que puede especificar únicamente aquellos permisos que desea que tenga su aplicación. La seguridad de acceso del código afecta a todo el código administrado que tenga como destino el Common Language Runtime, incluso si ese código no hace una comprobación del permiso de seguridad de acceso del código. Para obtener más información sobre la seguridad en [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], consulte los [conceptos clave de seguridad](../../../docs/standard/security/key-security-concepts.md) y los [conceptos básicos de la seguridad de acceso del código](../../../docs/framework/misc/code-access-security-basics.md).  
  
 Si el usuario ejecuta un archivo ejecutable de Windows Forms directamente desde un servidor web o un recurso compartido de archivos, el grado de confianza concedido a la aplicación depende de dónde resida el código y cómo se inicia. Cuando se ejecuta una aplicación, se evalúa automáticamente y recibe un conjunto de permisos con nombre de Common Language Runtime. De forma predeterminada, al código del equipo local se le concede el conjunto de permisos de plena confianza, al código de una red local se le concede el conjunto de permisos de la intranet local y al código de Internet se le concede el conjunto de permisos de Internet.  
  
> [!NOTE]
>  En [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] versión 1.0 Service Pack 1 y Service Pack 2, el grupo de código de zona de Internet recibe el conjunto de permisos Nothing. En las demás versiones de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], el grupo de código de zona de Internet recibe el conjunto de permisos de Internet.  
>   
>  Los permisos predeterminados que se conceden en cada uno de estos conjuntos de permisos se enumeran en el tema que trata de la [directiva de seguridad predeterminada](https://msdn.microsoft.com/library/2c086873-0894-4f4d-8f7e-47427c1a3b55). Según los permisos que reciba la aplicación, se ejecuta correctamente o genera una excepción de seguridad.  
>   
>  Muchas aplicaciones de Windows Forms se implementan mediante [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)]. Las herramientas usadas para generar una implementación [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] tienen valores predeterminados de seguridad diferentes a los tratados anteriormente. Para obtener más información, vea la explicación siguiente.  
  
 Los permisos reales concedidos a la aplicación pueden ser diferentes de los valores predeterminados, puesto que se puede modificar la directiva de seguridad; esto significa que la aplicación puede tener permisos en un equipo, pero no en otro.  
  
## <a name="developing-a-more-secure-windows-forms-application"></a>Desarrollo de una aplicación de Windows Forms más segura  
 La seguridad es importante en todos los pasos del desarrollo de aplicaciones. Comience por consultar y seguir las [instrucciones de codificación segura](../../../docs/standard/security/secure-coding-guidelines.md).  
  
 A continuación, decida si su aplicación debe ejecutarse con plena confianza o si debe ejecutarse en confianza parcial. La ejecución de la aplicación en plena confianza facilita el acceso a los recursos del equipo local, pero expone la aplicación y sus usuarios a grandes riesgos de seguridad si no diseña y desarrolla la aplicación respetando estrictamente las instrucciones de codificación segura. La ejecución de la aplicación en confianza parcial facilita el desarrollo de una aplicación más segura y reduce los riesgos, pero requiere una mayor planeación para la implementación de ciertas características.  
  
 Si elige la confianza parcial (es decir, el conjunto de permisos de Internet o de la intranet local), decida cómo desea que la aplicación se comporte en este entorno. Windows Forms proporciona otros métodos más seguros de implementar características cuando se trata de un entorno de confianza parcial. Ciertas partes de la aplicación, como el acceso a datos, se pueden diseñar y escribir de manera diferente para entornos de plena confianza y confianza parcial. Algunas características de Windows Forms, como la configuración de la aplicación, están diseñados para trabajar con confianza parcial. Para más información, consulte [Introducción a la configuración de la aplicación](../../../docs/framework/winforms/advanced/application-settings-overview.md).  
  
 Si la aplicación necesita más permisos que los que permite la confianza parcial, pero no desea que se ejecute en plena confianza, puede ejecutarla en confianza parcial y validar tan solo los permisos adicionales que necesite. Por ejemplo, si desea ejecutar en confianza parcial, pero debe conceder a la aplicación el acceso de solo lectura sobre un directorio del sistema de archivos del usuario, puede solicitar <xref:System.Security.Permissions.FileIOPermission> tan solo para ese directorio. Usado correctamente, este enfoque puede proporcionar a la aplicación una mayor funcionalidad y minimizar los riesgos de seguridad para los usuarios.  
  
 Cuando desarrolle una aplicación que se ejecutará en confianza parcial, realice un seguimiento de los permisos que debe ejecutar la aplicación y de los permisos que la aplicación podría usar de forma opcional. Si se conocen todos los permisos, realice una solicitud declarativa de permisos en el nivel de aplicación. La solicitud de permisos informa al tiempo de ejecución de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] acerca de los permisos que necesita la aplicación y los permisos que no desea específicamente. Para más información sobre la solicitud de permisos, consulte el artículo sobre [solicitud de permisos](https://msdn.microsoft.com/library/0447c49d-8cba-45e4-862c-ff0b59bebdc2).  
  
 Cuando solicite permisos opcionales, debe controlar las excepciones de seguridad que se generarán si la aplicación realiza una acción que requiere permisos que no tiene concedidos. El control adecuado de <xref:System.Security.SecurityException> garantizará que la aplicación continúa ejecutándose. La aplicación puede usar la excepción para determinar si se debería deshabilitar una característica para el usuario. Por ejemplo, una aplicación puede deshabilitar la opción de menú **Guardar** si no se concede el permiso de archivo necesario.  
  
 A veces es difícil saber si ha declarado todos los permisos adecuados. Por ejemplo, una llamada de método que a primera vista parece inofensiva, puede tener acceso al sistema de archivos en algún momento durante su ejecución. Si la aplicación no se implementa con todos los permisos necesarios, la depuración en el escritorio no dará problemas, pero producirá un error cuando se implemente. Tanto el [!INCLUDE[dnprdnlong](../../../includes/dnprdnlong-md.md)] SDK y [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] contienen herramientas para calcular los permisos que necesita una aplicación: los comandos MT.exe herramienta de línea y la característica Calcular permisos de Visual Studio, respectivamente.  
  
 Los temas siguientes describen características de seguridad adicionales de Windows Forms.  
  
|Tema|Descripción|  
|-----------|-----------------|  
|-   [Acceso más seguro a archivos y datos en Windows Forms](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)|Describe cómo tener acceso a archivos y datos en un entorno de confianza parcial.|  
|-   [Impresión más segura en Windows Forms](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)|Describe cómo tener acceso a las características de impresión en un entorno de confianza parcial.|  
|-   [Consideraciones de seguridad adicionales en Windows Forms](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)|Describe cómo manipular ventanas, usar el portapapeles y realizar llamadas a código no administrado en un entorno de confianza parcial.|  
  
-  
  
### <a name="deploying-an-application-with-the-appropriate-permissions"></a>Implementación de una aplicación con los permisos adecuados  
 La forma más común de implementar una aplicación de Windows Forms en un equipo cliente es con [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)], una tecnología de implementación que describe todos los componentes necesarios para que la aplicación se ejecute. [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] usa archivos XML denominados manifiestos para describir los ensamblados y los archivos que componen la aplicación, así como los permisos que requiere la aplicación.  
  
 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] tiene dos tecnologías para solicitar permisos elevados en un equipo cliente. Ambas tecnologías se basan en el uso de certificados de Authenticode. Los certificados sirven para que los usuarios tengan la seguridad de que la aplicación procede de un origen de confianza.  
  
 En la tabla siguiente se describen estas tecnologías.  
  
|Tecnología de permiso elevado|Descripción|  
|------------------------------------|-----------------|  
|Elevación de permisos|Le pide confirmación al usuario mediante un cuadro de diálogo de seguridad la primera vez que se ejecuta la aplicación. El cuadro de diálogo **Elevación de permisos** informa al usuario sobre quién publicó la aplicación para que el usuario pueda tomar una decisión informada antes de conceder confianza adicional.|  
|Implementación de aplicaciones de confianza|Implica a un administrador del sistema que realiza una instalación única del certificado de Authenticode de un editor en un equipo cliente. Desde ese momento, todas las aplicaciones firmadas con el certificado se considerarán de confianza y se podrán ejecutar con plena confianza en el equipo local sin necesidad de confirmar de nuevo.|  
  
 La tecnología elegida dependerá de su entorno de implementación. Para más información, consulte el artículo [Elegir una estrategia de implementación de ClickOnce](/visualstudio/deployment/choosing-a-clickonce-deployment-strategy).  
  
 De forma predeterminada, [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] las aplicaciones implementadas mediante Visual Studio o el [!INCLUDE[dnprdnlong](../../../includes/dnprdnlong-md.md)] herramientas del SDK (Mage.exe y MageUI.exe) están configuradas para ejecutarse en un equipo cliente que tiene plena confianza. Si va a implementar la aplicación con confianza parcial o solo con algunos permisos adicionales, tendrá que cambiar este valor predeterminado. Puede hacerlo con Visual Studio o el [!INCLUDE[dnprdnlong](../../../includes/dnprdnlong-md.md)] herramienta MageUI.exe cuando configure la implementación del SDK. Para obtener más información acerca de cómo usar MageUI.exe, vea el tutorial sobre implementación de una aplicación ClickOnce desde la línea de comandos.  Consulte también [Cómo: Establecer permisos personalizados para una aplicación ClickOnce](https://msdn.microsoft.com/library/hafybdaa\(v=vs.110\)) o [Cómo: Establecer permisos personalizados para una aplicación ClickOnce](https://msdn.microsoft.com/library/hafybdaa\(v=vs.120\)).  
  
 Para más información acerca de los aspectos de seguridad de [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] y la elevación de permisos, consulte [Proteger las aplicaciones ClickOnce](/visualstudio/deployment/securing-clickonce-applications). Para más información sobre la implementación de aplicaciones de confianza, consulte [Introducción a la implementación de aplicaciones de confianza](/visualstudio/deployment/trusted-application-deployment-overview).  
  
### <a name="testing-the-application"></a>Probar la aplicación  
 Si ha implementado la aplicación de Windows Forms con Visual Studio, puede habilitar la depuración en confianza parcial o un conjunto del entorno de desarrollo de permisos restringido.  Consulte también [Cómo: depurar una aplicación ClickOnce con permisos restringidos](https://msdn.microsoft.com/library/593zkfdf\(v=vs.110\)) o [Cómo: depurar una aplicación ClickOnce con permisos restringidos](https://msdn.microsoft.com/library/593zkfdf\(v=vs.120\)).  
  
## <a name="see-also"></a>Vea también  
 [Windows Forms Security](../../../docs/framework/winforms/windows-forms-security.md)  
 [Code Access Security Basics](../../../docs/framework/misc/code-access-security-basics.md) (Conceptos básicos sobre la seguridad de acceso del código)  
 [Seguridad e implementación ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)  
 [Introducción a la implementación de aplicaciones de confianza](/visualstudio/deployment/trusted-application-deployment-overview)  
 [Mage.exe (Herramienta de generación y edición de manifiestos)](../../../docs/framework/tools/mage-exe-manifest-generation-and-editing-tool.md)  
 [MageUI.exe (Herramienta de generación y edición de manifiestos, cliente gráfico)](../../../docs/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)
