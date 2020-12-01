---
title: Caspol.exe (Herramienta de la directiva de seguridad de acceso del código)
description: Revise Caspol.exe, la Herramienta de la directiva de seguridad de acceso del código (CAS). Esta herramienta permite a los usuarios y administradores modificar la directiva de seguridad de diferentes niveles de directiva.
ms.date: 03/30/2017
helpviewer_keywords:
- permission sets, modifying security policy
- security policy [.NET Framework], Code Access Security Policy tool
- enterprise security policy
- referencing code groups and permission sets
- user security policy
- Caspol.exe
- Code Access Security Policy tool
- code groups, modifying security policy
- application development [.NET Framework], security
- machine security policy
- security policy [.NET Framework], modifying
- manually editing security configuration files
ms.assetid: d2bf6123-7b0c-4e60-87ad-a39a1c3eb2e0
ms.openlocfilehash: 6567a4c738b3d6c8f14d1ab13ba005cb22bb7328
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247309"
---
# <a name="caspolexe-code-access-security-policy-tool"></a>Caspol.exe (Herramienta de la directiva de seguridad de acceso del código)

La herramienta de la directiva de seguridad de acceso del código (CAS), o herramienta Caspol.exe, permite a los usuarios y administradores modificar las directivas de seguridad correspondientes a los niveles de equipo, usuario y empresa.  
  
> [!IMPORTANT]
> A partir de .NET Framework 4, Caspol.exe no afecta a la directiva CAS, a menos que el [\<legacyCasPolicy> elemento](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) se establezca en `true`. Las configuraciones mostradas o modificadas por CasPol.exe solo afectarán a las aplicaciones que opten por usar la directiva CAS. Para más información, consulte [Cambios de seguridad](/previous-versions/dotnet/framework/security/security-changes).  
  
> [!NOTE]
> Los equipos de 64 bits incluyen las versiones de 64 bits y de 32 bits de la directiva de seguridad. Para asegurarse de que los cambios en la directiva se aplican a las aplicaciones de 32 bits y 64 bits, ejecute las dos versiones de Caspol.exe, la 32 bits y la de 64 bits.  
  
 La herramienta de la directiva de seguridad de acceso del código se instala automáticamente con .NET Framework y con Visual Studio. Puede encontrar Caspol.exe en %windir%\Microsoft.NET\Framework\\*versión* en los sistemas de 32 bits o en %windir%\Microsoft.NET\Framework64\\*versión* en los sistemas de 64 bits. (Por ejemplo, la ubicación es %windir%\Microsoft.NET\Framework64\v4.030319\caspol.exe para .NET Framework 4 en un sistema de 64 bits). Si en el equipo se ejecutan varias versiones de .NET Framework en paralelo, es posible que haya varias versiones de la herramienta instaladas. Puede ejecutar la herramienta desde el directorio de instalación. Sin embargo, se recomienda usar los [símbolos del sistema](developer-command-prompt-for-vs.md), que no requiere navegar hasta la carpeta de instalación.  
  
 En el símbolo del sistema, escriba lo siguiente:  
  
## <a name="syntax"></a>Sintaxis  
  
```console
caspol [options]  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Opción|Descripción|  
|------------|-----------------|  
|**-addfulltrust** *assembly_file*<br /><br /> o<br /><br /> **-af** *assembly_file*|Agrega un ensamblado que implementa un objeto de seguridad personalizado (como un permiso personalizado o una condición de pertenencia personalizada) a la lista de ensamblados de plena confianza para un nivel de directiva específico. El argumento *archivo_ensamblado* especifica el ensamblado que se va a agregar. Este archivo debe estar firmado con un [nombre seguro](../../standard/assembly/strong-named.md). Puede firmar un ensamblado con un nombre seguro mediante la herramienta [Nombre seguro (Sn.exe)](sn-exe-strong-name-tool.md).<br /><br /> Cada vez que se agrega a la directiva un conjunto de permisos que contiene un permiso personalizado, se debe agregar el ensamblado que implementa el permiso personalizado a la lista de plena confianza para dicho nivel de directiva. Los ensamblados que implementan objetos de seguridad personalizados (como grupos de código personalizados o condiciones de pertenencia personalizadas) que se utilizan en una directiva de seguridad (como la directiva de equipo) siempre deben agregarse a la lista de ensamblados de plena confianza. **Precaución:** Si el ensamblado que implementa el objeto de seguridad personalizado hace referencia a otros ensamblados, debe agregar primero los ensamblados a los que se hace referencia a la lista de ensamblados de plena confianza. Los objetos de seguridad personalizados creados con Visual Basic, C++ y JScript hacen referencia a Microsoft.VisualBasic.dll, Microsoft.VisualC.dll o Microsoft.JScript.dll, respectivamente. Estos ensamblados no se encuentran en la lista de ensamblados de plena confianza de forma predeterminada. Debe agregar el ensamblado adecuado a la lista de plena confianza antes de agregar un objeto de seguridad personalizado. Si se produce un error al realizar esta operación, el sistema de seguridad se interrumpirá y los ensamblados no se cargarán. En caso de que se produzca esta situación, la opción **-all -reset** de la herramienta Caspol.exe no reparará la seguridad. Para reparar la seguridad, debe editar manualmente los archivos de seguridad a fin de quitar el objeto de seguridad personalizado.|  
|**-addgroup** {*parent_label &#124; parent_name*} *mship pset_name* [*flags*]<br /><br /> o<br /><br /> **-ag** {*parent_label &#124; parent_name*} *mship pset_name* [*flags*]|Agrega un grupo de código nuevo a la jerarquía de grupos de código. Puede especificar el argumento *parent_label* o el argumento *parent_name*. El argumento *parent_label* especifica la etiqueta (como 1. o 1.1) del nombre del grupo de código que es el elemento primario del grupo de código que se va a agregar. El argumento *parent_name* especifica el nombre del grupo de código que es el elemento primario del grupo de código que se va a agregar. Dado que los argumentos *parent_label* y *parent_name* se pueden usar indistintamente, Caspol.exe debe poder distinguir entre ellos. Por tanto, el argumento *parent_name* no puede empezar con un número. Además, *parent_name* solo puede contener caracteres de A a Z, de 0 a 9 y de subrayado.<br /><br /> El argumento *mship* especifica la condición de pertenencia para el nuevo grupo de código. Para más información, consulte la tabla de los argumentos *mship* más adelante en esta sección.<br /><br /> El argumento *pset_name* es el nombre del conjunto de permisos que se asociará al grupo de código nuevo. También se pueden establecer uno o varios argumentos *flags* para el nuevo grupo. Para más información, consulte la tabla de argumentos *flags* más adelante en esta sección.|  
|**-addpset** {*psfile* &#124; *psfile* p *set_name*}<br /><br /> o<br /><br /> **-ap** {*named* _ *psfile* &#124; *psfile* *pset_name*}|Agrega un nuevo conjunto de permisos con nombre a la directiva. El conjunto de permisos se debe crear en XML y almacenar en un archivo .xml. Si el archivo XML contiene el nombre del conjunto de permisos, solo se especifica dicho archivo (*psfile*). Si el archivo XML no contiene el nombre del conjunto de permisos, se debe especificar tanto el nombre del archivo XML (*psfile*) como el nombre del conjunto de permisos (*pset_name*).<br /><br /> Tenga en cuenta que todos los permisos usados en un conjunto de permisos se deben definir en ensamblados incluidos en la caché global de ensamblados.|  
|**-a**[**ll**]|Indica que todas las opciones que siguen a esta se aplican a las directivas de equipo, usuario y empresa. La opción **-all** siempre hace referencia a la directiva del usuario actual que tiene iniciada una sesión actualmente. Consulte la opción **-customall** para hacer referencia a la directiva de un usuario distinto del usuario actual.|  
|**-chggroup** {*label &#124;name*} {*mship* &#124; *pset_name* &#124;<br /><br /> *flags* `}`<br /><br /> o<br /><br /> **-cg** {*label &#124;name*} {*mship* &#124; *pset_name* &#124;<br /><br /> *flags* `}`|Cambia en un grupo de código la condición de pertenencia, el conjunto de permisos o la configuración de las marcas **exclusive**, **levelfinal**, **name** o **description**. Puede especificar el argumento *label* o *name*. El argumento *label* especifica la etiqueta (como 1. o 1.1) del grupo de código. El argumento *name* especifica el nombre del grupo de código que se va a cambiar. Dado que los argumentos *label* y *name* se pueden usar indistintamente, Caspol.exe debe poder distinguir entre ellos. Por tanto, el argumento *name* no puede empezar con un número. Además, *name* solo puede contener caracteres de A a Z, de 0 a 9 y de subrayado.<br /><br /> El argumento *pset_name* especifica el nombre del conjunto de permisos que se va a asociar al nuevo grupo de código. Consulte las tablas que aparecen más adelante en esta sección para obtener información sobre los argumentos *mship* y *flags*.|  
|**-chgpset**  *psfile pset_name*<br /><br /> o<br /><br /> **-cp** *psfile pset_name*|Cambia un conjunto de permisos con nombre. El argumento *psfile* proporciona la nueva definición para el conjunto de permisos; es un archivo serializado de conjunto de permisos en formato XML. El argumento *pset_name* especifica el nombre del conjunto de permisos que se desea cambiar.|  
|**-customall**  *path*<br /><br /> o<br /><br /> **-ca**  *path*|Indica que todas las opciones que siguen a esta se aplican a las directivas de equipo, empresa y usuario personalizado especificado. Debe especificar la ubicación del archivo de configuración de seguridad del usuario personalizado con el argumento *path*.|  
|**-cu**[**stomuser**] *path*|Permite la administración de una directiva de usuario personalizado que no pertenece al usuario en cuyo nombre se está ejecutando actualmente la herramienta Caspol.exe. Debe especificar la ubicación del archivo de configuración de seguridad del usuario personalizado con el argumento *path*.|  
|**-enterprise**<br /><br /> o<br /><br /> **-en**|Indica que todas las opciones que siguen a esta se aplican a la directiva de nivel de empresa. Los usuarios que no son administradores de empresa no tienen derechos suficientes para modificar la directiva de empresa, aunque pueden verla. En escenarios distintos del de empresa, la opción predeterminada es que esta directiva no interfiera con las directivas de equipo y de usuario.|  
|**-e**[**xecution**] {**on** &#124; **off**}|Activa o desactiva el mecanismo que comprueba que el permiso se ejecuta antes de iniciarse la ejecución del código. **Nota:**  Este modificador ya no existe en .NET Framework 4 ni en las versiones posteriores. Para más información, consulte [Cambios de seguridad](/previous-versions/dotnet/framework/security/security-changes).|  
|**-f**[**orce**]|Suprime la prueba de autodestrucción de la herramienta y cambia la directiva de acuerdo con lo especificado por el usuario. Normalmente, Caspol.exe comprueba si los cambios efectuados en una directiva impedirían el correcto funcionamiento de la herramienta; si es el caso, Caspol.exe no guarda el cambio de la directiva e imprime un mensaje de error. Para forzar a Caspol.exe a cambiar la directiva aunque esto impida su ejecución, use la opción **–force**.|  
|**-h**[**elp**]|Muestra las opciones y la sintaxis de los comandos de Caspol.exe.|  
|**-l**[**ist**]|Enumera la jerarquía de grupos de código y los conjuntos de permisos para el nivel de directiva especificado (equipo, usuario o empresa) o para todos los niveles de directiva. Caspol.exe muestra primero la etiqueta del grupo de código, seguida del nombre, si el valor no es nulo.|  
|**-listdescription**<br /><br /> o<br /><br /> **-ld**|Enumera todas las descripciones de grupos de código para el nivel de directiva especificado.|  
|**-listfulltrust**<br /><br /> o<br /><br /> **-lf**|Enumera el contenido de la lista de ensamblados de plena confianza para el nivel de directiva especificado.|  
|**-listgroups**<br /><br /> o<br /><br /> **-lg**|Muestra los grupos de código para el nivel de directiva especificado o para todos los niveles de directiva. Caspol.exe muestra primero la etiqueta del grupo de código, seguida del nombre, si el valor no es nulo.|  
|**-listpset** or **-lp**|Muestra los conjuntos de permisos para el nivel de directiva especificado o para todos los niveles de directiva.|  
|**-m**[**achine**]|Indica que todas las opciones que siguen a esta se aplican a la directiva de nivel de equipo. Los usuarios que no son administradores no tienen derechos suficientes para modificar la directiva de equipo, aunque pueden verla. Para los administradores, **-machine** es la opción predeterminada.|  
|**-polchgprompt** {**on** &#124; **off**}<br /><br /> o<br /><br /> **-pp** {**on** &#124; **off**}|Habilita o deshabilita el mensaje que se muestra cada vez que Caspol.exe se ejecuta con una opción que provoca cambios en la directiva.|  
|**-quiet**<br /><br /> o<br /><br /> **-q**|Deshabilita temporalmente el mensaje que se muestra normalmente para una opción que ocasiona cambios en la directiva. No cambia la configuración global del mensaje. Use la opción únicamente en comandos individuales para evitar que el mensaje se deshabilite para todos los comandos de Caspol.exe.|  
|**-r**[**ecover**]|Recupera la directiva de un archivo de copia de seguridad. Cada vez que se efectúa un cambio en una directiva, Caspol.exe almacena la directiva antigua en un archivo de copia de seguridad.|  
|**-remfulltrust** *assembly_file*<br /><br /> o<br /><br /> **-rf**  *assembly_file*|Quita un ensamblado de la lista de plena confianza de un nivel de directiva. Realice esta operación si la directiva deja de usar un conjunto de permisos que contiene un permiso personalizado. No obstante, solo debe quitar de la lista de plena confianza un ensamblado que implementa un permiso personalizado si el ensamblado no implementa ningún otro permiso personalizado que se esté usando todavía. Cuando se quita un ensamblado de la lista, también se deben quitar los ensamblados de los que depende.|  
|**-remgroup** {*label &#124;name*}<br /><br /> o<br /><br /> **-rg** {l *abel &#124; name*}|Quita el grupo de código especificado mediante su etiqueta o su nombre. Si el grupo de código especificado tiene grupos de código secundarios, Caspol.exe también los quita.|  
|**-rempset** *pset_name*<br /><br /> o<br /><br /> **-rp** *pset_name*|Quita de la directiva el conjunto de permisos especificado. El argumento *pset_name* indica el conjunto de permisos que se va a quitar. Caspol.exe quita el conjunto de permisos solo si no está asociado a ningún grupo de código. Los conjuntos de permisos predeterminados (integrados) no se pueden quitar.|  
|**-reset**<br /><br /> o<br /><br /> **-rs**|Devuelve la directiva a su estado predeterminado y la guarda en el disco. Esta opción es resulta de gran utilidad si se sospecha que una directiva modificada ya no se puede reparar y se desea empezar de nuevo con los valores predeterminados de instalación. El restablecimiento de los valores predeterminados también puede resultar conveniente si se desea usar la directiva predeterminada como punto de partida para realizar modificaciones en archivos de configuración de seguridad específicos. Para más información, consulte [Editar manualmente archivos de configuración de seguridad](#cpgrfcodeaccesssecuritypolicyutilitycaspolexeanchor1).|  
|**-resetlockdown**<br /><br /> o<br /><br /> **-rsld**|Devuelve la directiva a una versión más restrictiva del estado predeterminado y la guarda en el disco; crea una copia de seguridad de la directiva de equipo anterior y la guarda en un archivo denominado `security.config.bac`.  La directiva bloqueada se parece a la predeterminada, salvo en que no otorga permisos al código de las zonas `Local Intranet`, `Trusted Sites` e `Internet`, y los grupos de códigos correspondientes no tienen grupos de códigos secundarios.|  
|**-resolvegroup** *assembly_file*<br /><br /> o<br /><br /> **-rsg**  *assembly_file*|Muestra los grupos de código a los que pertenece un ensamblado específico (*archivo_ensamblado*). De forma predeterminada, esta opción muestra los niveles de directiva de equipo, usuario y empresa a los que pertenece el ensamblado. Para ver solo un nivel de directiva, use esta opción con la opción **-machine**, **-user** o **-enterprise**.|  
|**-resolveperm** *assembly_file*<br /><br /> o<br /><br /> **-rsp** *assembly_file*|Muestra todos los permisos que el nivel especificado (o el predeterminado) de directiva de seguridad concedería al ensamblado si tuviera permiso para ejecutarse. El argumento *archivo_ensamblado* especifica el ensamblado. Si especifica la opción **-all**, Caspol.exe calcula los permisos para el ensamblado basándose en la directivas de usuario, equipo y empresa; de lo contrario, se aplican las reglas de comportamiento predeterminado.|  
|**-s**[**ecurity**] {**on** &#124; **off**}|Activa o desactiva la seguridad de acceso del código. Si se especifica la opción **-s off**, la seguridad basada en roles no se deshabilita. **Nota:**  Este modificador ya no existe en .NET Framework 4 ni en las versiones posteriores. Para más información, consulte [Cambios de seguridad](/previous-versions/dotnet/framework/security/security-changes). **Advertencia:**  Cuando la seguridad de acceso del código está deshabilitada, todas las peticiones de acceso al código se realizan correctamente. El hecho de deshabilitar la seguridad de acceso del código hace que el sistema sea vulnerable a ataques por parte de código malintencionado, como virus y gusanos. Cuando se desactiva la seguridad, aumenta el rendimiento, pero esta operación solo debe realizarse si se han adoptado otras medidas para evitar poner en peligro la seguridad global del sistema. Desconectarse de las redes públicas, proteger los equipos físicamente, etc. constituyen otros ejemplos de precauciones de seguridad.|  
|**-u**[**ser**]|Indica que todas las opciones que siguen a esta se aplican a la directiva de nivel de usuario correspondiente al usuario en cuyo nombre se ejecuta Caspol.exe. Para usuarios no administradores, **-user** es la opción predeterminada.|  
|**-?**|Muestra las opciones y la sintaxis de los comandos de Caspol.exe.|  
  
 El argumento *mship*, que especifica la condición de pertenencia de un grupo de código, se puede usar con las opciones **-addgroup** y **-chggroup**. Cada argumento *mship* se implementa como una clase de .NET Framework. Para especificar el argumento *mship*, use uno de los argumentos siguientes.  
  
|Argumento|Descripción|  
|--------------|-----------------|  
|**-allcode**|Especifica todo el código. Para obtener más información sobre esta condición de pertenencia, vea <xref:System.Security.Policy.AllMembershipCondition?displayProperty=nameWithType>.|  
|**-appdir**|Especifica el directorio de la aplicación. Si especifica **–appdir** como condición de pertenencia, la evidencia de dirección URL del código se compara con la evidencia de directorio de aplicación de dicho código. Si ambos valores de evidencia coinciden, se cumple la condición de pertenencia. Para obtener más información sobre esta condición de pertenencia, vea <xref:System.Security.Policy.ApplicationDirectoryMembershipCondition?displayProperty=nameWithType>.|  
|**-custom**  *xmlfile*|Agrega una condición de pertenencia personalizada. El argumento *xmlfile* obligatorio especifica el archivo .xml que contiene la serialización en formato XML de la condición de pertenencia personalizada.|  
|**-hash** *hashAlg* { **-hex** *hashValue* &#124; **-file** *assembly_file* }|Especifica el código que tiene el hash de ensamblado especificado. Para usar un hash como condición de pertenencia de grupo de código, debe especificar el valor hash o el archivo de ensamblado. Para obtener más información sobre esta condición de pertenencia, vea <xref:System.Security.Policy.HashMembershipCondition?displayProperty=nameWithType>.|  
|**-pub** { **-cert** *cert_file_name* &#124;<br /><br /> **-file** *signed_file_name* &#124; **-hex**  *hex_string* }|Especifica el código que tiene el editor de software especificado, indicado por un archivo de certificado, una firma en un archivo o la representación hexadecimal de un certificado X509. Para obtener más información sobre esta condición de pertenencia, vea <xref:System.Security.Policy.PublisherMembershipCondition?displayProperty=nameWithType>.|  
|**-site** *website*|Especifica el código que tiene el sitio de origen especificado. Por ejemplo:<br /><br /> `-site** www.proseware.com`<br /><br /> Para obtener más información sobre esta condición de pertenencia, vea <xref:System.Security.Policy.SiteMembershipCondition?displayProperty=nameWithType>.|  
|**-strong -file** *file_name* {*name* &#124; **-noname**} {*version* &#124; **-noversion**}|Especifica el código que tiene un nombre seguro determinado, que se indica por el nombre de archivo, el nombre de ensamblado en forma de cadena y la versión del ensamblado con el formato *major*.*minor*.*build*.*revision*. Por ejemplo:<br /><br /> **-strong -file** myAssembly.exe myAssembly 1.2.3.4<br /><br /> Para obtener más información sobre esta condición de pertenencia, vea <xref:System.Security.Policy.StrongNameMembershipCondition?displayProperty=nameWithType>.|  
|**-url** *URL*|Especifica el código que se origina en la dirección URL especificada. La dirección URL debe incluir un protocolo, como `http://` o `ftp://`. Además, puede utilizarse un carácter comodín (\*) para especificar varios ensamblados desde una dirección URL en particular. **Nota**: Dado que una dirección URL puede identificarse mediante el uso de varios nombres, el uso de una dirección URL como condición de pertenencia no es una forma segura de confirmar la identidad del código. Siempre que pueda, utilice una condición de pertenencia consistente en un nombre seguro, en una compañía de software o en un hash. <br /><br /> Para obtener más información sobre esta condición de pertenencia, vea <xref:System.Security.Policy.UrlMembershipCondition?displayProperty=nameWithType>.|  
|**-zone** *zonename*|Especifica el código que tiene la zona de origen especificada. El argumento *nombreDeZona* puede ser cualquiera de los valores siguientes: **MyComputer**, **Intranet**, **Trusted**, **Internet** o **Untrusted**. Para obtener más información sobre esta condición de pertenencia, vea la clase <xref:System.Security.Policy.ZoneMembershipCondition>.|  
  
 El argumento *flags*, que se puede usar con las opciones **–addgroup** y **–chggroup**, se especifica mediante uno de los argumentos siguientes.  
  
|Argumento|Descripción|  
|--------------|-----------------|  
|**-description** "*descripción*"|Si se usa con la opción **–addgroup**, especifica la descripción del grupo de código que se va a agregar. Si se usa con la opción **–chggroup**, especifica la descripción del grupo de código que se va a modificar. El argumento *descripción* debe ir entre comillas dobles.|  
|**-exclusive** {**on**&#124;**off**}|Cuando esta opción se establece en **on**, indica que solo se tiene en cuenta el conjunto de permisos asociado al grupo de código que se va a agregar o a modificar cuando parte del código satisface la condición de pertenencia del grupo de código. Cuando esta opción se establece en **off**, Caspol.exe tiene en cuenta los conjuntos de permisos de todos los grupos de código coincidentes en el nivel de directiva.|  
|**-levelfinal** {**on**&#124;**off**}|Cuando esta opción se establece en **on**, indica que no se tiene en cuenta ningún nivel de directiva por debajo del nivel en el que se encuentra el grupo de código agregado o modificado. Esta opción se usa normalmente en el nivel de directiva de equipo. Por ejemplo, si establece esta marca para un grupo de código en el nivel de equipo y una parte de código cumple la condición de pertenencia de este grupo de código, Caspol.exe no calcula ni aplica la directiva de nivel de usuario para este código.|  
|**-name** "*nombre*"|Si se usa con la opción **–addgroup**, especifica el nombre de scripting del grupo de código que se va a agregar. Si se usa con la opción **-chggroup**, especifica el nombre de scripting del grupo de código que se va a modificar. El argumento *nombre* debe ir entre comillas dobles. El argumento *nombre* no puede empezar con un número y solo puede contener caracteres de A a Z, de 0 a 9 y de subrayado. Se puede hacer referencia a los grupos de código mediante el argumento *nombre* en lugar de usar su etiqueta numérica. El argumento *nombre* también es muy útil en materia de scripting.|  
  
## <a name="remarks"></a>Comentarios  

 La directiva de seguridad se expresa mediante tres niveles: equipo, usuario y empresa. El conjunto de permisos que recibe un ensamblado viene determinado por la intersección de los conjuntos de permisos permitidos por estos tres niveles de directiva. Cada nivel está representado por una estructura jerárquica de grupos de código. Cada grupo de código tiene una condición de pertenencia que determina qué código es miembro de ese grupo. Asimismo, cada grupo de código tiene asociado un conjunto de permisos con nombre. Este conjunto de permisos especifica los permisos que el runtime permite que tenga el código que satisface la condición de pertenencia. Una jerarquía de grupos de código, junto con sus conjuntos de permisos con nombre asociados, define y conserva cada nivel de directiva de seguridad. Puede usar las opciones **–user**, **-customuser**, **–machine** y **-enterprise** para establecer el nivel de la directiva de seguridad.  
  
 Para más información sobre la directiva de seguridad y el modo en que el runtime determina qué permisos se conceden al código, consulte [Administración de directivas de seguridad](/previous-versions/dotnet/netframework-4.0/c1k0eed6(v=vs.100)).  
  
## <a name="referencing-code-groups-and-permission-sets"></a>Hacer referencia a grupos de código y conjuntos de permisos  

 Para facilitar las referencias a grupos de código en una jerarquía, la opción **-list** muestra una lista de grupos de código con sangría junto con sus etiquetas numéricas (1, 1.1, 1.1.1, etc.). Las demás operaciones de línea de comandos cuyo destino son los grupos de código también usan etiquetas numéricas para hacer referencia a grupos de código específicos.  
  
 Para hacer referencia a los conjuntos de permisos con nombre, se usan sus nombres. La opción **–list** muestra la lista de grupos de código seguida de una lista de conjuntos de permisos con nombre disponibles en esa directiva.  
  
## <a name="caspolexe-behavior"></a>Comportamiento de Caspol.exe  

 Todas las opciones excepto **-s**[**ecurity**] {**on** &#124; **off**} usan la versión de .NET Framework con la que se instaló Caspol.exe. Si ejecuta la herramienta Caspol.exe que se instaló con la versión *X* del runtime, los cambios solo afectan a dicha versión. Si hay otras instalaciones en paralelo del runtime, no se ven afectadas. Si ejecuta Caspol.exe desde la línea de comandos sin estar en un directorio de una versión del runtime específica, la herramienta se ejecuta desde el primer directorio de la versión del runtime existente en la ruta de acceso (normalmente la última versión instalada del runtime).  
  
 La opción **-s**[**ecurity**] {**on** &#124; **off**} es una operación que afecta a todo el equipo. Cuando se desactiva la seguridad de acceso del código se pone fin a las comprobaciones de seguridad de todo el código administrado y de todos los usuarios del equipo. Si se instalan en paralelo varias versiones de .NET Framework, este comando desactiva la seguridad de todas las versiones instaladas en el equipo. Aunque la opción **-list** muestra que la seguridad está desactivada, no hay ningún otro indicio que indique claramente este hecho a los demás usuarios.  
  
 Cuando un usuario sin derechos administrativos ejecuta Caspol.exe, todas las opciones hacen referencia a la directiva de nivel de usuario, salvo que se especifique la opción **–machine**. Cuando un administrador ejecuta Caspol.exe, todas las opciones hacen referencia a la directiva de equipo, salvo que se especifique la opción **–user**.  
  
 Para que Caspol.exe funcione, debe tener concedido el equivalente al conjunto de permisos **Everything**. La herramienta dispone de un mecanismo de protección que evita que la directiva se modifique con el objeto de impedir la concesión a Caspol.exe de los permisos que necesita para ejecutarse. Cuando se intenta realizar algún cambio de ese tipo en la directiva, Caspol.exe informa de que dicho cambio bloqueará la herramienta y lo rechaza. Este mecanismo de protección se puede desactivar para un comando determinado mediante la opción **–force**.  
  
<a name="cpgrfcodeaccesssecuritypolicyutilitycaspolexeanchor1"></a>

## <a name="manually-editing-the-security-configuration-files"></a>Editar manualmente archivos de configuración de seguridad  

 Existen tres archivos de configuración de seguridad que se corresponden con los tres niveles de directiva admitidos por Caspol.exe: uno para la directiva de equipo, otro para la directiva del usuario especificado, y un tercero para la directiva de empresa. Estos archivos se crean únicamente en el disco cuando se modifica la directiva de equipo, usuario o empresa mediante Caspol.exe. Puede usar la opción **–reset** de Caspol.exe para guardar la directiva de seguridad predeterminada en el disco si fuera necesario.  
  
 En la mayoría de los casos, no es recomendable editar manualmente los archivos de configuración de seguridad. Pero puede haber escenarios en los que sea necesario modificar estos archivos, como cuando un administrador desea editar la configuración de seguridad para un usuario concreto.  
  
## <a name="examples"></a>Ejemplos  

 **-addfulltrust**  
  
 Suponga que se ha agregado a la directiva de equipo un conjunto de permisos que contiene un permiso personalizado. Este permiso personalizado se implementa en `MyPerm.exe` y `MyPerm.exe` hace referencia a clases de `MyOther.exe`. Ambos ensamblados de deben agregar a la lista de ensamblados de plena confianza. El comando siguiente agrega el ensamblado `MyPerm.exe` a la lista de plena confianza de la directiva de equipo.  
  
```console  
caspol -machine -addfulltrust MyPerm.exe  
```  
  
 El comando siguiente agrega el ensamblado `MyOther.exe` a la lista de plena confianza de la directiva de equipo.  
  
```console  
caspol -machine -addfulltrust MyOther.exe  
```  
  
 **-addgroup**  
  
 El comando siguiente agrega un grupo de código secundario a la raíz de la jerarquía de grupos de código de la directiva de equipo. El nuevo grupo de código es miembro de la zona **Internet** y está asociado al conjunto de permisos **Execution**.  
  
```console  
caspol -machine -addgroup 1.  -zone Internet Execution  
```  
  
 El siguiente comando agrega un grupo de código secundario que concede permisos de intranet local al recurso compartido \\\netserver\netshare.  
  
```console  
caspol -machine -addgroup 1. -url \\netserver\netshare\* LocalIntranet  
```  
  
 **-addpset**  
  
 El comando siguiente agrega el conjunto de permisos `Mypset` a la directiva de usuario.  
  
```console  
caspol -user -addpset Mypset.xml Mypset  
```  
  
 **-chggroup**  
  
 El comando siguiente cambia el conjunto de permisos de la directiva de usuario del grupo de código cuya etiqueta es 1.2. para el conjunto de permisos **Execution**.  
  
```console  
caspol -user -chggroup 1.2. Execution  
```  
  
 El comando siguiente cambia la condición de pertenencia de la directiva predeterminada del grupo de código cuya etiqueta es 1.2.1. y cambia el valor de la marca **exclusive**. La condición de pertenencia se define como código que se origina en la zona **Internet** y se activa la marca **exclusive**.  
  
```console  
caspol -chggroup 1.2.1. -zone Internet -exclusive on  
```  
  
 **-chgpset**  
  
 El comando siguiente cambia el conjunto de permisos denominado `Mypset` por el conjunto de permisos contenido en `newpset.xml`. Tenga en cuenta que la versión actual no permite cambiar conjuntos de permisos que se estén usando en la jerarquía de grupos de código.  
  
```console  
caspol -chgpset Mypset newpset.xml  
```  
  
 **-force**  
  
 El comando siguiente hace que el grupo de código raíz de la directiva de usuario (con la etiqueta numérica 1) se asocie al conjunto de permisos denominado **Nothing**. Esto impide la ejecución de Caspol.exe.  
  
```console  
caspol -force -user -chggroup 1 Nothing  
```  
  
 **-recover**  
  
 El comando siguiente recupera la última directiva de equipo guardada.  
  
```console  
caspol -machine -recover  
```  
  
 **-remgroup**  
  
 El comando siguiente quita el grupo de código con la etiqueta numérica 1.1. Si este grupo de código tiene grupos de código secundarios, estos también se eliminan.  
  
```console  
caspol -remgroup 1.1.  
```  
  
 **-rempset**  
  
 El comando siguiente quita el conjunto de permisos **Execution** de la directiva de usuario.  
  
```console  
caspol -user -rempset Execution  
```  
  
 El comando siguiente quita `Mypset` del nivel de directiva de usuario.  
  
```console  
caspol -rempset MyPset  
```  
  
 **-resolvegroup**  
  
 El comando siguiente muestra todos los grupos de código de la directiva de equipo a la que pertenece `myassembly`.  
  
```console  
caspol -machine -resolvegroup myassembly  
```  
  
 El comando siguiente muestra todos los grupos de código de las directivas de equipo, empresa y usuario personalizado especificado a las que pertenece `myassembly`.  
  
```console  
caspol -customall "c:\config_test\security.config" -resolvegroup myassembly  
```  
  
 **-resolveperm**  
  
 El comando siguiente calcula los permisos correspondientes a `testassembly` basándose en los niveles de directiva de equipo y usuario.  
  
```console  
caspol -all -resolveperm testassembly  
```  
  
## <a name="see-also"></a>Vea también

- [Herramientas](index.md)
- [Símbolos del sistema](developer-command-prompt-for-vs.md)
