---
title: Implementación de aplicaciones de escritorio modernas
description: Todo lo que necesita saber acerca de la implementación de aplicaciones de escritorio modernas.
ms.date: 05/12/2020
ms.openlocfilehash: ba47f09b27adf270734bbfff285fe44dd4175d29
ms.sourcegitcommit: 632818f4b527e5bf3c48fc04e0c7f3b4bdb8a248
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "98615859"
---
# <a name="deploying-modern-desktop-applications"></a>Implementación de aplicaciones de escritorio modernas

Al desarrollar aplicaciones de escritorio, es necesario tener en cuenta cómo se va a empaquetar e implementar la aplicación en los equipos de los usuarios. El problema con el empaquetado, la implementación y la instalación es que normalmente se encuentra bajo el paraguas de los profesionales de ti, que se ocupan de diferentes aspectos que los desarrolladores.

Estos días están familiarizados con el concepto DevOps, donde los desarrolladores y profesionales de TI trabajan en estrecha colaboración para trasladar las aplicaciones a sus entornos de producción. Pero si ha estado en la batalla de escritorio durante más de 10 años, es posible que haya visto la siguiente historia. Un equipo de desarrolladores trabaja juntos de forma difícil para cumplir con las fechas límite de proyecto. Los usuarios empresariales están nerviosos, ya que necesitan que el sistema trabaje en muchas máquinas de usuario para ejecutar la empresa. En "D-Day", el jefe de proyecto comprueba con cada desarrollador que su código funciona bien y que todo está bien, por lo que se puede enviar. Después, el equipo de paquetes llega a generar la configuración de la aplicación, distribuirla a cada equipo de usuario y a un conjunto de usuarios de prueba ejecutar la aplicación. Bueno, intentan, porque antes de mostrar cualquier interfaz de usuario, la aplicación produce una excepción que indica "método ~ del objeto ~ failed". El pánico comienza a atravesar el aire y una breve investigación apunta a un desarrollador joven y cansado que ha introducido un control de terceros que, con todo, "trabajó en el equipo de desarrollo".

La instalación de aplicaciones de escritorio ha sido tradicionalmente una pesadilla por dos motivos principales:

- Falta de una cultura de colaboración estrecha entre los equipos de desarrollo y TI.
- Falta de un paquete sólido y de la implementación de tecnología en la que se puede crear.

De hecho, hemos estado viviendo con el hecho de que, a veces, lamentamos que instalara una aplicación porque:

- Acaba teniendo algunos efectos secundarios no deseados en el equipo.
- Algunas aplicaciones que se instalaron previamente dejan de funcionar.

Además, no puede restaurar el sistema a su estado original desinstalando la aplicación. Se usa para vivir esta situación de que hemos acuñó términos como "DLL Hell" o "Winrot".

En este capítulo, hablaremos sobre MSIX. MSIX es la nueva tecnología de Microsoft que intenta capturar las mejores tecnologías anteriores para proporcionar una base sólida para la tecnología de empaquetado del futuro.

¿Qué tiene que hacer una tecnología de empaquetado con modernización? Bueno, resulta que el empaquetado es fundamental para la empresa TI con gran cantidad de dinero invertido allí. La modernización no solo está relacionada con el uso de las tecnologías más recientes. También está relacionado con la reducción del tiempo de comercialización desde el momento en que se define un requisito empresarial hasta que su empresa entregue la característica a su cliente.

## <a name="the-modern-application-lifecycle"></a>Ciclo de vida de la aplicación moderna

Hoy en día, los desarrolladores escriben y compilan el código para una aplicación y, a continuación, pasan los recursos generados a los profesionales de ti. Después, los profesionales de ti reconfiguran la aplicación y la empaquetan, normalmente en un archivo MSI o más recientemente en un formato de empaquetado de App-V. A continuación, la aplicación se implementa a través de diferentes canales y herramientas. Uno de los principales problemas de este enfoque se conoce comúnmente como "empaquetar Paralysis". El problema es que este ciclo se repite cada vez que hay una actualización de la aplicación o una actualización del sistema operativo.

Puede ver el proceso que se refleja en la siguiente imagen:

![Diagrama que muestra el ciclo de vida de ti moderno](./media/deploy-modern-applications/modern-it-application-lifecycle.png)

Las compañías necesitan una manera de dividir este ciclo de empaquetado en tres ciclos independientes:

- Actualizaciones del sistema operativo
- Actualizaciones de aplicaciones
- Personalización

![Diagrama que muestra el ciclo de uso realmente virtuoso de ti moderno](./media/deploy-modern-applications/modern-it-virtuous-cycle.png)

En el diagrama anterior se muestra que puede:

- Actualice el sistema operativo subyacente sin tener que volver a empaquetar las aplicaciones.
- Habilite las personalizaciones de este sin necesidad de volver a empaquetar el paquete de desarrollador original.

Este cambio radical nos lleva al ciclo de vida de ti nuevo y moderno, tal como se muestra en la siguiente imagen:

![Diagrama que muestra el ciclo de vida de la aplicación mediante herramientas de Microsoft](./media/deploy-modern-applications/microsoft-it-tools.png)

Los desarrolladores crean la aplicación y generan un paquete MSIX que los profesionales de TI pueden consumir y configurar sin necesidad de volver a empaquetar. Junto con la tecnología MSIX, Microsoft ha creado herramientas que le permiten personalizar y configurar paquetes sin volver a empaquetar.

## <a name="msix-the-next-generation-of-deployment"></a>MSIX: la siguiente generación de implementación

Antes de MSIX, había varias tecnologías de empaquetado disponibles como asistentes para la instalación, MSI, ClickOnce, App-V y scripting. Cada una de estas tecnologías tiene sus propias ventajas y Microsoft ha decidido elegir lo mejor de todo para compilar MSIX. MSIX se basa en las bases de estas tecnologías existentes que seleccionan lo mejor de cada una:

- App-V = \> contenedores
- ClickOnce = \> actualización automática
- MSI = \> fácil de distribuir

Con MSIX, obtiene una tecnología de instalador con todas estas características.

![Diagrama que muestra las distintas tecnologías que tuvieron un impacto en la compilación de MSIX](./media/deploy-modern-applications/msix.png)

### <a name="benefits-of-msix"></a>Ventajas de MSIX

#### <a name="never-regret-installing-an-app"></a>Nunca lamentamos instalar una aplicación

MSIX proporciona una implementación predecible, confiable y segura. El método declarativo incluido en el manifiesto del paquete permite al sistema operativo realizar un seguimiento de todos los recursos que necesita su aplicación. También proporciona una auténtica desinstalación limpia sin efectos secundarios.

#### <a name="disk-space-optimization"></a>Optimización de espacio en disco

MSIX está optimizado para reducir la superficie que tiene una aplicación en el espacio en disco del equipo del usuario. Crea un almacenamiento de instancia única de los archivos. Es decir, si tiene dos paquetes diferentes con el mismo archivo DLL, el archivo DLL no se instalará dos veces. La plataforma se encarga del problema porque conoce todos los archivos instalados por una aplicación determinada gracias a su naturaleza declarativa. También permite tener diferentes versiones de un archivo DLL que funcionan en paralelo.

Con el uso de paquetes de recursos, puede crear fácilmente aplicaciones multilingües y el sistema operativo se encarga de instalar las que se usan.

#### <a name="network-optimization"></a>Optimización de red

MSIX detecta las diferencias en los archivos en el nivel de bloque de bytes habilitando una característica denominada actualizaciones diferenciales. Esto significa que solo los bloques de bytes actualizados se descargan en las actualizaciones de la aplicación.

![Un diagrama que muestra cómo MSIX administra las actualizaciones diferenciales](./media/deploy-modern-applications/msix-managing-updates.png)

Con la instalación de streaming, el usuario puede empezar a trabajar rápidamente en la aplicación mientras otras partes de la aplicación se descargan en segundo plano. Esta característica contribuye a una experiencia atractiva para los usuarios.

Con la característica de paquetes opcionales, logrará la aplicación de los componentes en la implementación de la aplicación, por lo que puede descargarlos cuando sea necesario.

#### <a name="simple-packaging-and-deployment"></a>Empaquetado e implementación sencillos

El archivo AppManifest declara el control de versiones, el destino del dispositivo y la identificación de forma estándar para todas las aplicaciones. También proporciona una manera de firmar los recursos que proporcionan una sólida base de seguridad.

#### <a name="os-managed"></a>SO administrado

El sistema operativo controla todos los procesos para instalar, actualizar y quitar una aplicación. Las aplicaciones se instalan por usuario, pero se descargan solo una vez, lo que minimiza la superficie del disco. Microsoft está trabajando para proporcionar la experiencia de MSIX también en Windows 7.

#### <a name="windows-provides-integrity-for-the-app"></a>Windows proporciona integridad para la aplicación

Con el uso de firmas digitales, puede garantizar que no se instala una aplicación desde orígenes que no son de confianza. MSIX también evita alteraciones porque:

- Mantiene un registro de los hash de archivo.
- Detecta si un archivo se ha modificado después de la instalación.

#### <a name="works-for-the-entire-app-catalog"></a>Funciona para todo el catálogo de aplicaciones

Una de las cosas más interesantes sobre MSIX es que funciona para todo el catálogo de aplicaciones, Windows Forms, WPF, MFC/ATL, Delphi, incluso si desea realizar la implementación de xCopy, ClickOnce o ir a la tienda, puede usar el mismo paquete MSIX.

### <a name="tools"></a>Herramientas

#### <a name="windows-application-packaging-project"></a>Proyecto de paquete de aplicación de Windows

Puedes usar el **proyecto de paquete de aplicación de Windows** en Visual Studio para generar un paquete para la aplicación de escritorio. A continuación, puede publicar el paquete en el Microsoft Store o transferirlo a uno o varios equipos.

#### <a name="msix-packaging-tool"></a>Herramienta de empaquetado MSIX

La herramienta MSIX Packaging Tool permite volver a empaquetar las aplicaciones Win32 existentes con el formato MSIX. Ofrece una interfaz de usuario interactiva y una línea de comandos para las conversiones, y le permite convertir una aplicación sin tener el código fuente.

![Herramienta de empaquetado MSIX](./media/deploy-modern-applications/msix-packaging-tool.png)

#### <a name="package-support-framework"></a>Marco de compatibilidad de paquete

El marco de soporte técnico de paquetes es un kit de código abierto que le ayuda a aplicar correcciones a la aplicación de Win32 existente cuando no tiene acceso al código fuente, de modo que se pueda ejecutar en un contenedor MSIX. La plataforma de compatibilidad de paquete te ayuda a que la aplicación siga las prácticas recomendadas del entorno de tiempo de ejecución moderno.

#### <a name="app-installer"></a>Instalador de aplicación

El instalador de aplicaciones permite que las aplicaciones de Windows 10 se instalen haciendo doble clic en el paquete de la aplicación. Esto significa que los usuarios no necesitan usar PowerShell u otras herramientas de desarrollo para implementar aplicaciones de Windows 10. El instalador de la aplicación también puede instalar una aplicación de la web, paquetes opcionales y conjuntos relacionados.

## <a name="how-to-create-an-msix-package-from-an-existing-win32-desktop-application"></a>Cómo crear un paquete de MSIX a partir de una aplicación de escritorio de Win32 existente

Vamos a analizar el proceso para crear un paquete de MSIX a partir de una aplicación Win32 existente. En este ejemplo, usaremos una aplicación Windows Forms.

Para empezar, agregue un nuevo proyecto a la solución, seleccione el proyecto de paquete de aplicación de Windows y asígnele un nombre.

![Agregando nuevo proyecto de paquete de aplicación de Windows](./media/deploy-modern-applications/add-packaging-project.png)

Verá la estructura del proyecto de empaquetado y tendrá en cuenta una carpeta especial llamada *aplicaciones*. Dentro de esta carpeta, puede especificar las aplicaciones que desea incluir en el paquete. Puede ser más de uno.

![Estructura del proyecto de empaquetado.](./media/deploy-modern-applications/packaging-project.png)

Haga clic con el botón derecho en la carpeta *aplicaciones* y seleccione el proyecto Windows Forms que desea empaquetar desde la solución de Visual Studio.

![Agregar el proyecto Windows Forms al proyecto de empaquetado](./media/deploy-modern-applications/add-winforms-project.png)

En este momento, puede compilar y generar el paquete, pero vamos a examinar un par de cosas. Para mejorar la experiencia del usuario, Visual Studio puede generar automáticamente todos los recursos visuales que necesita una aplicación moderna para controlar iconos y recursos en mosaico para la barra de mosaico y el menú Inicio. Abra el archivo *Package. appxmanifest* para tener acceso al diseñador de manifiestos. Después, puede generar todos los recursos visuales a partir de una imagen determinada presente en el proyecto; para ello, haga clic en **crear**.

![Captura de pantalla del diseñador de manifiestos en Visual Studio](./media/deploy-modern-applications/manifest-designer.png)

Si abre el código para el archivo *Package. appxmanifest* , puede ver un par de cosas interesantes.

Justo debajo `<Package>` de, hay un `<Identity>` nodo. Aquí es donde la aplicación empaquetada va a obtener su identidad, que será administrada por el sistema operativo.

![Nodo de identidad](./media/deploy-modern-applications/identity-node.png)

En el `<Capabilities>` nodo, puede encontrar todos los requisitos que necesita la aplicación y prestar especial atención a `<rescap:Capability Name="runFullTrust" \>` , que indica al sistema operativo que ejecute la aplicación en modo de plena confianza, ya que es una aplicación Win32.

![Nodo capacidades](./media/deploy-modern-applications/capabilities-node.png)

Establezca el proyecto de empaquetado como el proyecto de inicio para la solución y seleccione *Ejecutar*. Esto se va a:

- Compile la aplicación Windows Forms.
- Cree un paquete de MSIX a partir de los resultados de la compilación.
- Implementar los paquetes.
- Instálelo localmente en el equipo de desarrollo.
- Iniciar la aplicación.

![Nuestra aplicación instalada](./media/deploy-modern-applications/our-installed-application.png)

Con esto, tiene la experiencia de instalación y desinstalación limpia que MSIX proporciona completamente integrada en Windows 10.

En la fase final se explica cómo implementar el paquete MSIX en otro equipo.

Haga clic con el botón derecho en el proyecto de empaquetado, seleccione el menú **tienda** y, a continuación, seleccione la opción **crear paquetes de aplicaciones** .

Después, puede elegir entre crear un paquete para cargarlo en el almacén o crear paquetes para la instalación de prueba. En la mayoría de los escenarios de modernización, elija **deseo crear paquetes para la instalación de prueba**.

![Configuración de paquetes](./media/deploy-modern-applications/configuring-packages.png)

Allí puede seleccionar las distintas arquitecturas que desee como destino, ya que puede incluir tantas como desee en el mismo paquete MSIX.

El paso final consiste en declarar dónde desea implementar los recursos finales de instalación.

![Configurar las opciones de actualización](./media/deploy-modern-applications/configure-update-settings.png)

Puede optar por usar un servidor Web de una ruta de acceso UNC compartida en los servidores de archivos de la empresa. Preste atención a la configuración para especificar cómo desea actualizar la aplicación. Describiremos las actualizaciones de la aplicación en la sección siguiente.

Para obtener una guía paso a paso detallada, consulte [empaquetar una aplicación de escritorio desde el código fuente con Visual Studio](/windows/msix/desktop/desktop-to-uwp-packaging-dot-net).

## <a name="auto-updates-in-msix"></a>Actualizaciones automáticas en MSIX

La tienda Windows tiene un excelente mecanismo de actualización mediante Windows Update. En la mayoría de los escenarios empresariales, no se usa el almacén para distribuir las aplicaciones de escritorio. Por lo tanto, necesita una manera similar de configurar las actualizaciones de la aplicación y extraerlas a los usuarios.

Mediante una combinación de características de Windows 10 y paquetes MSIX, puede proporcionar una excelente experiencia de actualización para los usuarios. De hecho, no es necesario que el usuario sea técnico en absoluto, sino que se puede beneficiar de una experiencia de actualización de aplicaciones sin problemas.

Puede configurar las actualizaciones para interactuar con el usuario de dos maneras diferentes:

- Actualizaciones solicitadas por el usuario: el sistema operativo muestra la interfaz de usuario agradable autogenerada para notificar al usuario sobre la instalación de la aplicación. Esta interfaz de usuario se basa en las propiedades que se especifican en los archivos de instalación.

- Actualizaciones silenciosas en segundo plano. Con esta opción, los usuarios no tienen que tener en cuenta las actualizaciones.

También puede configurar Cuándo desea realizar las actualizaciones cuando se inicia la aplicación o de forma periódica. Gracias a las características de instalación de prueba, puede incluso obtener estas actualizaciones mientras la aplicación se está ejecutando.

Cuando se usa este tipo de implementación, se crea un archivo especial denominado *. AppInstaller*. Este archivo simple contiene las siguientes secciones:

- La ubicación del archivo *. AppInstaller*
- Propiedades principales del paquete MSIX de la aplicación
- El comportamiento de actualización

![archivo. AppInstaller](./media/deploy-modern-applications/appinstaller-file.png)

En combinación con este archivo, Microsoft ha diseñado un protocolo de dirección URL especial para iniciar el proceso de instalación desde un vínculo:

```xml
<a href="ms-appinstaller:?source=http://mywebservice.azureedge.net/MyApp.msix">Install app package </a>
```

Este protocolo funciona en todos los exploradores e inicia el proceso de instalación con una excelente experiencia de usuario en Windows 10. Dado que el sistema operativo administra el proceso de instalación, es consciente de la ubicación desde la que se instaló esta aplicación y realiza un seguimiento de todos los archivos afectados por el proceso.

MSIX crea una interfaz de usuario para la instalación que muestra algunas propiedades del paquete. Esto permite una experiencia de instalación común para todas las aplicaciones.

Una vez que haya generado el nuevo paquete MSIX y lo haya pasado al servidor de implementación, solo tiene que editar el archivo *. AppInstaller* para reflejar estos cambios, principalmente la versión y la ruta de acceso al nuevo archivo MSIX. La próxima vez que el usuario inicie la aplicación, el sistema detectará el cambio y descargará los archivos de la nueva versión en segundo plano. Una vez hecho esto, la instalación se ejecutará en el nuevo inicio de la aplicación de forma transparente para el usuario.

>[!div class="step-by-step"]
>[Anterior](example-migration.md)
