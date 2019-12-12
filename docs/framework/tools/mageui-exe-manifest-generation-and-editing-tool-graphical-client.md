---
title: MageUI.exe (Herramienta de generación y edición de manifiestos, cliente gráfico)
ms.date: 03/30/2017
helpviewer_keywords:
- Manifest Generation and Editing tool
- MageUI.exe
ms.assetid: f9e130a6-8117-49c4-839c-c988f641dc14
ms.openlocfilehash: 7d09e1283be8ec75df89957e91f0d8411c125b3b
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714453"
---
# <a name="mageuiexe-manifest-generation-and-editing-tool-graphical-client"></a>MageUI.exe (Herramienta de generación y edición de manifiestos, cliente gráfico)

MageUI.exe admite la misma funcionalidad que la herramienta de línea de comandos Mage.exe, pero con una interfaz de usuario (IU) basada en Windows. Con esta herramienta puede crear, editar y firmar manifiestos de implementación y de aplicación. Los nuevos manifiestos que se crean con MageUI.exe tienen como destino el perfil de cliente de .NET Framework 4. Cuando el destino es una versión anterior de .NET Framework, se deben usar las versiones anteriores de MageUI.exe. Cuando se agregan o quitan ensamblados de un manifiesto, o cuando se vuelven a firmar manifiestos existentes, MageUI.exe no actualiza el manifiesto para destinarlo al perfil de cliente de .NET Framework 4. Para más información, consulte [Mage.exe (Herramienta de generación y edición de manifiestos)](mage-exe-manifest-generation-and-editing-tool.md).

 Esta herramienta se instala automáticamente con Visual Studio. Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7). Para más información, consulte [Símbolos del sistema](developer-command-prompt-for-vs.md).

 Se incluyen dos versiones de Mage.exe y MageUI.exe como componente del programa de instalación de Visual Studio. Para ver información de versión, ejecute MageUI.exe, seleccione **Ayuda**y, a continuación, seleccione **Acerca de**. En esta documentación se describe la versión 4.0.x.x de Mage.exe y MageUI.exe.

> [!NOTE]
> MageUI.exe no admite el elemento [compatibleFrameworks](/visualstudio/deployment/compatibleframeworks-element-clickonce-deployment) cuando se guarda un manifiesto de aplicación que ya se ha firmado con un certificado mediante MageUI.exe. En su lugar, debe usar [Mage.exe](mage-exe-manifest-generation-and-editing-tool.md).  
  
## <a name="uielement-list"></a>Lista de UIElement  
 La siguiente tabla enumera los elementos de menú y de barra de herramientas disponibles.  
  
|Comando|Menú|Acceso directo|DESCRIPCIÓN|  
|-------------|----------|--------------|-----------------|  
|**Manifiesto de aplicación**|**Archivo, Nuevo**||Crea un nuevo manifiesto de aplicación.|  
|**Manifiesto de implementación**|**Archivo, Nuevo**||Crea un nuevo manifiesto de implementación.|  
|**Abrir**|**Archivo**|CTRL+O|Abre un manifiesto de implementación, un manifiesto de aplicación o una licencia de confianza existente para su edición.|  
|**Cerrar**|**Archivo**|CTRL+F4|Cierra un archivo abierto.<br /><br /> Si modifica un archivo antes de cerrarlo, MageUI.exe le pedirá que vuelva a firmarlo con una clave pública, un par de claves, o un certificado almacenado.|  
|**Guardar**|**Archivo**|CTRL+S|Guarda en el disco el documento que tiene el foco de entrada de datos del usuario.|  
|**Guardar como**|**Archivo**||Permite guardar un archivo en el disco con un nuevo nombre y/o una nueva ubicación.|  
|**Guardar todo**|**Archivo**||Guarda los cambios realizados en todos los archivos que están abiertos en MageUI.exe.|  
|**Preferencias**|**Archivo**||Abre el cuadro de diálogo **Preferencias**. Para obtener más información, vea la sección siguiente.|  
|**Salir**|**Archivo**|ALT+F4|Cierra MageUI.exe.|  
|**Cortar**|**Editar**|CTRL+X|Quita el texto seleccionado de la aplicación y lo mueve al Portapapeles del sistema.|  
|**Copiar**|**Editar**|CTRL+C|Copia el texto seleccionado en el Portapapeles del sistema.|  
|**Pegar**|**Editar**|CTRL+V|Pega el texto del Portapapeles del sistema en el elemento de texto activo.|  
|**Eliminar**|**Editar**||Elimina un elemento seleccionado en una lista, como una licencia de confianza de la pestaña **Manifiesto de implementación**.|  
|**Cerrar todo**|**Ventana**||Cierra todos los archivos que están abiertos en MageUI.exe. Si hay uno o varios archivos sin guardar, MageUI.exe le preguntará si desea guardarlos. MageUI.exe también le pedirá que seleccione una clave de firma para cada archivo sin firmar o modificado.|  
|**Acerca de**|**Ayuda**||Muestra la información de versión y de copyright de MageUI.exe.|  
  
## <a name="preferences-dialog-box"></a>Cuadro de diálogo Preferencias  
 El cuadro de diálogo **Preferencias** contiene los elementos siguientes.  
  
|Elemento de la interfaz de usuario|DESCRIPCIÓN|  
|----------------|-----------------|  
|**Firmar al guardar**|Le pide que firme un archivo cada vez que guarde sus modificaciones.|  
|**Usar certificado de firma predeterminado**|Usa la clave especificada en el cuadro de texto **Archivo de certificado** para firmar todos los archivos. Esta opción elimina el mensaje de solicitud de firma que suele aparecer al guardar un archivo si la opción **Firmar al guardar** está seleccionada. Use el botón de puntos suspensivos ( **…** ) situado junto al cuadro de texto **Archivo de certificado** para seleccionar un archivo de claves.|  
|Algoritmo de resumen|Especifica el algoritmo con el que se generarán los resúmenes de dependencia. El valor debe ser "sha256RSA" o "sha1RSA". Usa SHA1 como valor predeterminado. Se usa tanto en los manifiestos de aplicación como de implementación. Si el usuario proporciona un certificado al guardar el manifiesto, usa los algoritmos del certificado para generar los resúmenes de dependencia.|  
  
## <a name="signing-options-dialog-box"></a>Cuadro de diálogo Opciones de firma  
 El cuadro de diálogo **Opciones de firma** aparece cuando se guarda un manifiesto o una licencia de confianza por primera vez, o cuando se modifica un manifiesto o licencia de confianza. Solo aparece si está seleccionada la opción **Firmar al guardar** del cuadro de diálogo **Preferencias**. Debe estar conectado a Internet al firmar un manifiesto que especifica un valor en el cuadro de texto **URI de marca de tiempo**.  
  
 Este cuadro de diálogo contiene los siguientes elementos.  
  
|Elemento de la interfaz de usuario|DESCRIPCIÓN|  
|----------------|-----------------|  
|**Firmar con archivo de certificado**|Firma el manifiesto con un certificado digital almacenado en el sistema de archivos.|  
|**Archivo**|Proporciona un área para escribir la ruta de acceso al archivo .pfx que representa el certificado.|  
|**...**|Abre un cuadro de diálogo **Elegir archivo** que permite seleccionar un archivo .pfx existente.|  
|**Nuevo**|Genera un nuevo .pfx que no se puede comprobar a través de una entidad de certificación (CA). Para obtener más información sobre los tipos de certificados usados para firmar implementaciones de ClickOnce, consulte [Información general sobre la implementación de aplicaciones de confianza](/visualstudio/deployment/trusted-application-deployment-overview).|  
|**Contraseña**|Proporciona un área para escribir la contraseña usada para firmar con este certificado. Si no procede, puede dejarse en blanco.|  
|**Firmar con certificado almacenado**|Muestra una lista seleccionable de certificados digitales guardados en el almacén de certificados del equipo.|  
|**URI de marca de tiempo**|Muestra el Localizador uniforme de recursos (URI) de un servicio de marca de tiempo digital. Las marcas de tiempo en los manifiestos evitan tener que volver a firmarlos en caso de que el certificado digital expire antes de implementar la versión siguiente de la aplicación. Para más información, consulte [Miembros del programa de certificados raíz de Windows](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265983(v=ws.11)) y [ClickOnce y Authenticode](/visualstudio/deployment/clickonce-and-authenticode).|  
|**No firmar**|Le permite guardar el manifiesto sin agregar una firma de un certificado digital.|  
  
## <a name="tab-and-panel-descriptions"></a>Descripciones de pestañas y paneles  
 Cuando se abre un documento con MageUI.exe, aparece dentro de su propia página de pestañas. Cada pestaña contiene un conjunto de paneles de propiedades. Los paneles contienen subconjuntos agrupados de los datos del documento.  
  
### <a name="application-manifest-tab"></a>Pestaña Manifiesto de aplicación  
 La pestaña **Manifiesto de aplicación** muestra el contenido de un manifiesto de aplicación. El manifiesto de aplicación describe todos los archivos incluidos con la implementación y los permisos necesarios para que la aplicación se ejecute en el cliente.  
  
 La pestaña **Manifiesto de aplicación** contiene las siguientes pestañas.  
  
|Elemento de la interfaz de usuario|DESCRIPCIÓN|  
|----------------|-----------------|  
|**Name**|Especifica la información de identificación de la implementación.|  
|**Descripción**|Especifica la información de publicador, producto y compatibilidad.|  
|**Opciones de la aplicación**|Especifica si se trata de una aplicación de explorador y si el manifiesto es el origen de información de confianza.|  
|**Archivos**|Especifica todos los archivos que componen esta implementación.|  
|**Permisos necesarios**|Especifica el conjunto de permisos mínimo requerido por la aplicación para ejecutarse en un cliente.|  
  
### <a name="name-tab"></a>Pestaña Nombre  
 La pestaña **Nombre** se muestra al crear o abrir por primera vez un manifiesto de aplicación. Identifica de forma única la implementación y, opcionalmente, especifica una plataforma de destino válida.  
  
|Elemento de la interfaz de usuario|DESCRIPCIÓN|  
|----------------|-----------------|  
|**Name**|Obligatorio. Es el nombre del manifiesto de aplicación. Normalmente, coincide con el nombre de archivo.|  
|**Versión**|Obligatorio. Es el número de versión de la implementación en formato *N.N.N.N*. Solo es obligatorio el primer número de la compilación principal. Por ejemplo, para la versión 1.0 de una aplicación, los valores válidos incluirían `1`, `1.0`, `1.0.0` y `1.0.0.0`.|  
|**Procesador**|Opcional. Es la arquitectura de la máquina en la que se puede ejecutar esta implementación. El valor predeterminado es `msil` o Lenguaje Intermedio de Microsoft, que es el formato predeterminado de todos los ensamblados administrados. Modifique este campo si ha precompilado los ensamblados en la aplicación para una arquitectura concreta. Para más información sobre la precompilación, consulte [Ngen.exe (Generador de imágenes nativas)](ngen-exe-native-image-generator.md).|  
|**Referencia cultural**|Opcional. Es el código ISO de dos partes, país y región, en el que se ejecuta esta aplicación. De manera predeterminada, es `neutral`.|  
|**Token de clave pública**|Opcional. Es la clave pública con la que se ha firmado este manifiesto de aplicación. Si se trata de un manifiesto nuevo o sin firmar, este campo aparecerá como `Unsigned`.|  
  
### <a name="description-tab"></a>Pestaña Descripción  
 Esta información normalmente se proporciona dentro del manifiesto de implementación. Estos campos solo pueden modificarse si se selecciona la casilla **Usar manifiesto de la aplicación para la información de confianza** en la pestaña **Opciones de la aplicación**.  
  
|Elemento de la interfaz de usuario|DESCRIPCIÓN|  
|----------------|-----------------|  
|**Publicador**|Nombre de la persona u organización responsable de la aplicación. Este valor se usa como nombre de la carpeta del menú Inicio.|  
|**Producto**|Nombre completo del producto. Si seleccionó **Instalar localmente** para el elemento **Tipo de aplicación** de la pestaña **Opciones de implementación** del manifiesto de implementación, este nombre aparecerá en el vínculo del menú **Inicio** y en **Agregar o quitar programas** para esta aplicación.|  
|**Ubicación de soporte técnico**|Es la dirección URL desde la que los clientes pueden obtener ayuda y soporte técnico para la aplicación.|  
  
### <a name="application-options-tab"></a>Pestaña Opciones de la aplicación  
  
|Elemento de la interfaz de usuario|DESCRIPCIÓN|  
|----------------|-----------------|  
|**Aplicación Explorador de Windows Presentation Foundation**|Especifica si se trata de una aplicación WPF que se ejecuta en el explorador como una aplicación de explorador XAML (XBAP).|  
|**Usar manifiesto de la aplicación para la información de confianza**|Especifica si este manifiesto contiene información de confianza.|  
  
### <a name="files-tab"></a>Pestaña Archivos  
  
|Elemento de la interfaz de usuario|DESCRIPCIÓN|  
|----------------|-----------------|  
|**Directorio de la aplicación**|Es el directorio en el que residen los archivos de la aplicación. Use el botón de puntos suspensivos ( **…** ) para seleccionar el directorio.|  
|**Rellenar**|Agrega todos los archivos del directorio de la aplicación y sus subdirectorios al manifiesto de aplicación. Si MageUI.exe encuentra un único archivo ejecutable en el directorio, lo marca automáticamente como punto de entrada, es decir, como el archivo que se ejecuta primero cuando se inicia la aplicación ClickOnce en el cliente.|  
|**Archivos de aplicación**|Enumera todos los archivos de la aplicación. Cada archivo tiene tres atributos modificables, descritos a continuación.|  
|**Tipo de archivo**|El tipo de archivo puede ser uno de cuatro valores:<br /><br /> -   Ninguno.<br />-   Punto de entrada. Archivo ejecutable principal de la aplicación. Tan solo se puede marcar un archivo ejecutable como punto de entrada.<br />-   Archivo de datos. Archivo que proporciona datos a la aplicación (por ejemplo, un archivo XML).<br />-   Archivo de icono. Icono de la aplicación, como el que aparece en el escritorio o en la esquina de una ventana de aplicación.|  
|**Opcional**|Los archivos marcados como opcionales no se descargan en la instalación o actualización inicial, pero se pueden descargar en tiempo de ejecución mediante la API a petición System.Deployment. Para obtener más información, vea [Tutorial: Descarga de ensamblados a petición con la API de implementación ClickOnce mediante el diseñador](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer).|  
|**Grupo**|Etiqueta para un conjunto de archivos opcionales. Puede aplicar esta etiqueta a un conjunto de archivos y usar la API a petición para descargar un lote de archivos con una sola llamada API.|  
  
### <a name="permissions-required-tab"></a>Pestaña Permisos necesarios  
 Use la pestaña **Permisos necesarios** si necesita conceder a la aplicación más acceso al equipo local del que se concede de forma predeterminada. Para más información, consulte [Proteger las aplicaciones ClickOnce](/visualstudio/deployment/securing-clickonce-applications).  
  
|Elemento de la interfaz de usuario|DESCRIPCIÓN|  
|----------------|-----------------|  
|**Tipo de conjunto de permisos**|El conjunto de permisos mínimo requerido por la aplicación para ejecutarse en el cliente. Para obtener una descripción de estos conjuntos de permisos y ver qué permisos se exigen, vea [Conjuntos de permisos con nombre](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/4652tyx7(v=vs.100)).|  
|**Detalles**|Es el XML creado para el manifiesto de aplicación para representar el conjunto de permisos. A menos que tenga amplios conocimientos del formato XML del manifiesto de aplicación, no debe modificar manualmente este XML. Para más información, consulte [Manifiesto de aplicación ClickOnce](/visualstudio/deployment/clickonce-application-manifest).|  
  
### <a name="deployment-manifest-tab"></a>Pestaña Manifiesto de implementación  
 La pestaña **Manifiesto de implementación** contiene las siguientes pestañas.  
  
|Elemento de la interfaz de usuario|DESCRIPCIÓN|  
|----------------|-----------------|  
|**Name**|Especifica la información de identificación de la implementación.|  
|**Descripción**|Especifica la información de publicador, producto y compatibilidad.|  
|**Opciones de implementación**|Especifica información adicional sobre la implementación, como el tipo de aplicación y la ubicación de inicio.|  
|**Opciones de actualización**|Especifica la frecuencia con la que ClickOnce debe comprobar si hay actualizaciones de la aplicación.|  
|**Referencia de aplicación**|Especifica el manifiesto de aplicación para esta implementación.|  
  
### <a name="name-tab"></a>Pestaña Nombre  
 La pestaña **Nombre** aparece al crear o abrir por primera vez un manifiesto de implementación. Identifica de forma única la implementación y, opcionalmente, especifica una plataforma de destino válida.  
  
|Elemento de la interfaz de usuario|DESCRIPCIÓN|  
|----------------|-----------------|  
|**Name**|Obligatorio. Es el nombre del manifiesto de implementación. Normalmente, coincide con el nombre de archivo.|  
|**Versión**|Obligatorio. Es el número de versión de la implementación en formato *N.N.N.N*. Solo es obligatorio el primer número de la compilación principal. Por ejemplo, para la versión 1.0 de una aplicación, los valores válidos incluirían `1`, `1.0`, `1.0.0` y `1.0.0.0`.|  
|**Procesador**|Opcional. Es la arquitectura de la máquina en la que se puede ejecutar esta implementación. El valor predeterminado es `msil` o Lenguaje Intermedio de Microsoft, que es el formato predeterminado de todos los ensamblados administrados. Modifique este campo si ha compilado los ensamblados en la aplicación para una arquitectura concreta.|  
|**Referencia cultural**|Opcional. Es el código ISO de dos partes, país y región, en el que se ejecuta esta aplicación. De manera predeterminada, es `neutral`.|  
|**Token de clave pública**|Opcional. Es la clave pública con la que se firmó el manifiesto de implementación. Si se trata de un manifiesto nuevo o sin firmar, este campo aparecerá como `Unsigned`.|  
  
### <a name="description-tab"></a>Pestaña Descripción  
  
|Elemento de la interfaz de usuario|DESCRIPCIÓN|  
|----------------|-----------------|  
|**Publicador**|Obligatorio. Es el nombre de la persona u organización responsable de la aplicación. Este valor se usa como nombre de la carpeta del menú Inicio.|  
|**Producto**|Obligatorio. Nombre completo del producto. Si seleccionó **Instalar localmente** para el elemento **Tipo de aplicación** en la pestaña **Opciones de implementación**, este nombre aparecerá en el vínculo del menú **Inicio** y en **Agregar o quitar programas** para esta aplicación.|  
|**Ubicación de soporte técnico**|Opcional. Es la dirección URL desde la que los clientes pueden obtener ayuda y soporte técnico para la aplicación.|  
  
### <a name="deployment-options-tab"></a>Pestaña Opciones de implementación  
  
|Elemento de la interfaz de usuario|DESCRIPCIÓN|  
|----------------|-----------------|  
|**Tipo de aplicación**|Opcional. Especifica si la aplicación se instala por sí misma en el equipo cliente (**Instalar localmente**), se ejecuta en línea (**Solo en línea**) o es una aplicación WPF que se ejecuta en el explorador (**Aplicación de explorador WPF**). El valor predeterminado es **Instalar localmente**.|  
|**Ubicación de inicio**|Opcional. Es la dirección URL desde la que debe iniciarse realmente la aplicación. Resulta útil al implementar una aplicación desde un CD que debe actualizarse desde la Web.|  
|**Incluir la ubicación de inicio (ProviderURL) en el manifiesto**|Opcional. Especifica la dirección URL que ClickOnce examinará para buscar actualizaciones de la aplicación.|  
|**Ejecutar automáticamente la aplicación después de instalarla**|Obligatorio. Especifica que la aplicación de ClickOnce debe ejecutarse inmediatamente después de la instalación inicial desde una dirección URL. El valor predeterminado es que la casilla esté activada.|  
|**Permitir que se pasen los parámetros de la dirección URL a la aplicación**|Obligatorio. Permite la transferencia de datos de parámetros a la aplicación de ClickOnce a través de una cadena de consulta anexa a la dirección URL del manifiesto de implementación. El valor predeterminado es que la casilla esté desactivada.|  
|**Usar la extensión de archivo .deploy**|Obligatorio. Cuando se selecciona, todos los archivos del manifiesto de aplicación deben tener la extensión .deploy. El valor predeterminado es que la casilla esté desactivada.|  
  
### <a name="update-options-tab"></a>Pestaña Opciones de actualización  
 La pestaña **Opciones de actualización** solo contiene las opciones mencionadas aquí cuando el cuadro de selección **Tipo de aplicación** de la pestaña **Nombre** se establece en **Instalar localmente**.  
  
|Elemento de la interfaz de usuario|DESCRIPCIÓN|  
|----------------|-----------------|  
|**Esta aplicación debe buscar actualizaciones**|Especifica si ClickOnce debe comprobar si hay actualizaciones de la aplicación. Si no se selecciona esta casilla, la aplicación no buscará actualizaciones a menos que se actualice mediante programación usando las API en el espacio de nombres <xref:System.Deployment.Application>.|  
|**Elija cuándo debe buscar actualizaciones la aplicación**|Proporciona dos opciones para la búsqueda de actualizaciones:<br /><br /> -   **Antes de que se inicie la aplicación**. La búsqueda de actualizaciones se realiza antes de la ejecución de la aplicación.<br />-   **Después de que se inicie la aplicación**. La búsqueda de actualizaciones comienza una vez que se ha inicializado el formulario principal de la aplicación y se ejecutará la próxima vez que se inicie la aplicación.|  
|**Actualice la frecuencia de comprobación**|Determina la frecuencia con la que ClickOnce debe buscar actualizaciones:<br /><br /> -   **Comprobar cada vez que se ejecute la aplicación**. ClickOnce llevará a cabo una búsqueda de actualizaciones cada vez que el usuario abra la aplicación.<br />-   **Comprobar cada**: Seleccione el intervalo y la unidad (horas, días o semanas) del tiempo que debe transcurrir antes de comprobar si hay actualizaciones.|  
|**Especifique la versión mínima requerida para esta aplicación**|Opcional. Especifica la instalación obligatoria de una versión concreta de la aplicación para evitar que los usuarios trabajen con una versión anterior.|  
|**Version**|Obligatorio si se selecciona la casilla **Especifique la versión mínima requerida para esta aplicación**. El número de versión proporcionado debe tener el formato *N.N.N.N*. Solo es obligatorio el primer número de la compilación principal. Por ejemplo, para la versión 1.0 de una aplicación, los valores válidos incluirían `1`, `1.0`, `1.0.0` y `1.0.0.0`.|  
  
### <a name="application-reference-tab"></a>Pestaña Referencia de aplicación  
 La pestaña **Referencia de la aplicación** contiene los mismos campos que la pestaña **Nombre** descrita anteriormente en este tema. La única excepción es el campo siguiente.  
  
|Elemento de la interfaz de usuario|DESCRIPCIÓN|  
|----------------|-----------------|  
|**Seleccionar manifiesto**|Le permite elegir el manifiesto de aplicación. El resto de campos de esta página se rellenarán cuando elija un manifiesto de aplicación.|  
  
## <a name="see-also"></a>Vea también

- [Seguridad e implementación ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)
- [Tutorial: Implementación manual de una aplicación ClickOnce](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)
- [Mage.exe (Herramienta de generación y edición de manifiestos)](mage-exe-manifest-generation-and-editing-tool.md)
