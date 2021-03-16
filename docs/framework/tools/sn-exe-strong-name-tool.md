---
title: Sn.exe (Herramienta de nombre seguro)
description: Empiece a trabajar con Sn.exe, la Herramienta de nombre seguro. Firme ensamblados con nombres seguros. Administre claves y genere y compruebe firmas.
ms.date: 03/30/2017
helpviewer_keywords:
- public keys, signing files
- Strong Name tool
- Sn.exe
- assemblies [.NET Framework], signing
- signing files
- strong-named assemblies, signing files
- key pairs for signing files
ms.assetid: c1d2b532-1b8e-4c7a-8ac5-53b801135ec6
ms.openlocfilehash: 76999ab305f9924bafaa95884b634e2a59251ff0
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102259052"
---
# <a name="snexe-strong-name-tool"></a>Sn.exe (Herramienta de nombre seguro)

La herramienta de nombre seguro (Sn.exe) permite firmar ensamblados con [nombres seguros](../../standard/assembly/strong-named.md). Sn.exe proporciona opciones para la administración de claves, así como para la generación y comprobación de firmas.  
  
> [!WARNING]
> Para garantizar la seguridad, no confíe únicamente en el uso de nombres seguros. Estos solo proporcionan una identidad única.

 Para obtener más información sobre los nombres seguros y los ensamblados con nombre seguro, vea [Ensamblados con nombre seguro](../../standard/assembly/strong-named.md) y [Cómo: Firma de un ensamblado con un nombre seguro](../../standard/assembly/sign-strong-name.md).  
  
 La herramienta Nombre seguro se instala automáticamente con Visual Studio. Para iniciar la herramienta, use un [shell de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell).  

> [!NOTE]
> En los equipos de 64 bits, ejecute la versión de Sn.exe de 32 bits mediante Símbolo del sistema para desarrolladores de Visual Studio y la versión de 64 bits mediante el símbolo del sistema de Visual Studio x64 Win64.
  
 En el símbolo del sistema, escriba lo siguiente:  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
sn [-quiet][option [parameter(s)]]  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Opción|Descripción|  
|------------|-----------------|  
|`-a identityKeyPairFile signaturePublicKeyFile`|Genera datos de <xref:System.Reflection.AssemblySignatureKeyAttribute> para migrar la clave de identidad a la clave de firma desde un archivo.|  
|`-ac identityPublicKeyFile identityKeyPairContainer signaturePublicKeyFile`|Genera datos de <xref:System.Reflection.AssemblySignatureKeyAttribute> para migrar la clave de identidad a la clave de firma desde un contenedor de claves.|  
|`-c [csp]`|Establece el proveedor de servicios criptográficos (CSP) predeterminado que se usa para firmar con nombres seguros. Este valor se aplica al equipo completo. Si no se especifica un nombre CSP, Sn.exe borra el valor actual.|  
|`-d container`|Elimina el contenedor de claves especificado del CSP de nombres seguros.|  
|`-D assembly1 assembly2`|Comprueba si dos ensamblados difieren solo en la firma. Esta opción se suele usar para realizar una comprobación después de volver a firmar un ensamblado con un par de claves diferente.|  
|`-e assembly outfile`|Extrae la clave pública de *assembly* y la almacena en *outfile*.|  
|`-h`|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
|`-i infile container`|Instala el par de claves de *infile* en el contenedor de claves especificado. El contenedor de claves reside en el CSP de nombres seguros.|  
|`-k [keysize] outfile`|Genera una nueva clave <xref:System.Security.Cryptography.RSACryptoServiceProvider> del tamaño especificado y la escribe en el archivo especificado.  En el archivo se escriben tanto una clave pública como una clave privada.<br /><br /> Si no especifica un tamaño de clave y tiene instalado Microsoft Enhanced Cryptographic Provider, se generará una clave de 1.024 bits de forma predeterminada; en caso contrario, se generará una clave de 512 bits.<br /><br /> El parámetro *keysize* admite longitudes de clave de 384 bits a 16 384 bits, en incrementos de 8 bits, si tiene instalado Microsoft Enhanced Cryptographic Provider.  Admite longitudes de clave de 384 bits a 512 bits, en incrementos de 8 bits, si tiene Microsoft Base Cryptographic Provider instalado.|  
|`-m [y|n]`|Especifica si los contenedores de claves son específicos del equipo o del usuario. Si especifica *y*, los contenedores de claves son específicos del equipo. Si especifica *n*, los contenedores de claves son específicos del usuario.<br /><br /> Si no especifica y ni n, esta opción muestra el valor actual.|  
|`-o infile [outfile]`|Extrae la clave pública de *infile* y la almacena en un archivo .csv. Una coma separa cada byte de la clave pública. Este formato resulta útil para incluir en el código fuente las referencias a las claves en forma de matrices inicializadas. Si no especifica un parámetro *outfile*, esta opción coloca la salida en el Portapapeles. **Nota:**  Esta opción no comprueba si la entrada es únicamente una clave pública. Si `infile` contiene un par de claves con una clave privada, la clave privada también se extrae.|  
|`-p infile outfile [hashalg]`|Extrae la clave pública del par de claves de *infile* y la almacena en *outfile*, opcionalmente mediante el algoritmo de RSA especificado por *hashalg*. Esta clave pública se puede usar para retrasar la firma de un ensamblado mediante las opciones **/delaysign+** y **/keyfile** de [Assembly Linker (Al.exe)](al-exe-assembly-linker.md). Cuando se retrasa la firma de un ensamblado, únicamente se establece en tiempo de compilación la clave pública, y se reserva espacio en el archivo para la firma que se agregará más tarde, cuando se conozca la clave privada.|  
|`-pc container outfile [hashalg]`|Extrae la clave pública del par de claves de *container* y la almacena en *outfile*. Si usa la opción *hashalg*, la clave pública se extrae mediante el algoritmo de RSA.|  
|`-Pb [y|n]`|Especifica si se impone la directiva de omisión de nombres seguros. Si especifica *y*, no se validan los nombres seguros de los ensamblados de plena confianza cuando se cargan en un objeto <xref:System.AppDomain> de plena confianza. Si especifica *n*, se valida la corrección de los nombres seguros, pero no se valida un nombre seguro específico. <xref:System.Security.Permissions.StrongNameIdentityPermission> no tiene ningún efecto en ensamblados de plena confianza. Debe realizar su propia comprobación para buscar coincidencias con un nombre seguro.<br /><br /> Si no especifica `y` ni `n`, esta opción muestra el valor actual. De manera predeterminada, es `y`. **Nota:**  En equipos de 64 bits, debe establecer este parámetro tanto en las instancias de 32 bits como en las de 64 bits de Sn.exe.|  
|`-q[uiet]`|Especifica el modo silencioso; suprime la presentación de mensajes de operaciones correctas.|  
|`-R[a] assembly infile`|Vuelve a firmar un ensamblado firmado anteriormente o un ensamblado con firma retrasada mediante el par de claves de *infile*.<br /><br /> Si se usa **-Ra**, los valores de hash se vuelven a calcular para todos los archivos del ensamblado.|  
|`-Rc[a] assembly container`|Vuelve a firmar un ensamblado firmado anteriormente o uno con firma retrasada mediante el par de claves de *container*.<br /><br /> Si se usa **-Rca**, los valores de hash se vuelven a calcular para todos los archivos del ensamblado.|  
|`-Rh assembly`|Vuelve a calcular los valores de hash para todos los archivos del ensamblado.|  
|`-t[p] infile`|Muestra el token de la clave pública almacenada en *infile*. El contenido de *infile* debe ser una clave pública generada previamente a partir de un archivo de par de claves mediante **-p**.  No use la opción **-t[p]** para extraer el token directamente de un archivo de par de claves.<br /><br /> Sn.exe calcula el token mediante una función hash de la clave pública. Para ahorrar espacio, Common Language Runtime almacena tokens de clave pública en el manifiesto como parte de una referencia a otro ensamblado cuando graba una dependencia en un ensamblado que tiene un nombre seguro. La opción **-tp** muestra la clave pública además del token. Si se ha aplicado el atributo <xref:System.Reflection.AssemblySignatureKeyAttribute> al ensamblado, el token es para la clave de identidad, y se muestran el nombre del algoritmo hash y la clave de identidad.<br /><br /> Tenga en cuenta que esta opción no comprueba la firma del ensamblado y no se debe usar para tomar decisiones de confianza.  Esta opción solo muestra los datos de token de clave pública sin formato.|  
|`-T[p] assembly`|Muestra el token de clave pública de *assembly*. El argumento *assembly* debe ser el nombre de un archivo que contiene un manifiesto del ensamblado.<br /><br /> Sn.exe calcula el token mediante una función hash de la clave pública. Para ahorrar espacio, runtime almacena tokens de clave pública en el manifiesto como parte de una referencia a otro ensamblado cuando graba una dependencia en un ensamblado que tiene un nombre seguro. La opción **-Tp** muestra la clave pública además del token. Si se ha aplicado el atributo <xref:System.Reflection.AssemblySignatureKeyAttribute> al ensamblado, el token es para la clave de identidad, y se muestran el nombre del algoritmo hash y la clave de identidad.<br /><br /> Tenga en cuenta que esta opción no comprueba la firma del ensamblado y no se debe usar para tomar decisiones de confianza.  Esta opción solo muestra los datos de token de clave pública sin formato.|  
|`-TS assembly infile`|Aplique una firma de generación de prueba al *ensamblado* firmado parcial o totalmente con el par de claves de *archivo_de_entrada*.|  
|`-TSc assembly container`|Aplique una firma de generación de prueba al *ensamblado* firmado total o parcialmente con el par de claves del contenedor de claves llamado *contenedor*.|
|`-v assembly`|Comprueba el nombre seguro de *assembly*, donde *assembly* es el nombre de un archivo que contiene un manifiesto del ensamblado.|  
|`-vf assembly`|Comprueba el nombre seguro de *assembly*. A diferencia de la opción **-v**, **-vf** fuerza la comprobación aunque se haya deshabilitado con la opción **-Vr**.|  
|`-Vk regfile.reg assembly [userlist] [infile]`|Crea un archivo de entradas de registro (.reg) que puede usar para registrar el ensamblado especificado para pasar por alto la comprobación. Las reglas de nomenclatura de ensamblados que se aplican a la opción **-Vr** también se aplican a la opción **–Vk**. Para obtener información sobre las opciones *userlist* e *infile*, vea la opción **–Vr**.|  
|`-Vl`|Enumera los valores actuales de la comprobación de nombre seguro en este equipo.|  
|`-Vr  assembly [userlist] [infile]`|Registra *assembly* para pasar por alto la comprobación. Opcionalmente, puede especificar una lista de nombres de usuario separados por comas a la que se aplicará la omisión de comprobación. Si especifica *infile*, la comprobación permanece habilitada, pero la clave pública de *infile* se usa en operaciones de comprobación. Puede especificar *assembly* con el formato *\*, strongname* para registrar todos los ensamblados con el nombre seguro especificado. Para *strongname*, especifique la cadena de dígitos hexadecimales que representa la forma con tokens de la clave pública. Vea las opciones **-t** y **-T** para mostrar el token de clave pública. **Advertencia:**  Use esta opción solo durante la fase de desarrollo. Al agregar un ensamblado a la lista de omisiones de comprobación se produce una vulnerabilidad en la seguridad. Puede que un ensamblado malicioso utilice el nombre completo especificado (nombre de ensamblado, versión, referencia cultural y token de clave pública) del ensamblado existente en la lista de omisiones de comprobación para imitar su identidad. Esto permitiría que el ensamblado malintencionado se pasase también por alto durante la comprobación.|  
|||  
|`-Vu  assembly`|Anula el registro de *assembly* para pasar por alto la comprobación. Las mismas reglas de nomenclatura de ensamblados que se aplican a **-Vr** son aplicables a **-Vu**.|  
|`-Vx`|Quita todas las entradas de omisión de comprobación.|  
|`-?`|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
  
> [!NOTE]
> Todas las opciones de Sn.exe distinguen entre mayúsculas y minúsculas, y se deben escribir exactamente como se muestra en esta tabla para que la herramienta pueda reconocerlas.  
  
## <a name="remarks"></a>Comentarios  

 Las opciones **-R** y **–Rc** son útiles con ensamblados firmados con retraso. En este escenario, únicamente se ha establecido en tiempo de compilación la clave pública, y la firma se agrega más tarde, cuando se conoce la clave privada.  
  
> [!NOTE]
> Para parámetros (por ejemplo, –**Vr**) que escriben en recursos protegidos, como el Registro, ejecute SN.exe como un administrador.  
  
La herramienta Nombre seguro asume que los pares de claves pública y privada se generan con el identificador del algoritmo `AT_SIGNATURE`. Los pares de claves pública y privada generados con el algoritmo `AT_KEYEXCHANGE` producen un error.

## <a name="examples"></a>Ejemplos  

 El comando siguiente crea un nuevo par de claves aleatorio y lo almacena en el `keyPair.snk`.  
  
```console  
sn -k keyPair.snk  
```  
  
 El comando siguiente almacena la clave en `keyPair.snk` en el contenedor `MyContainer` del CSP de nombres seguros.  
  
```console  
sn -i keyPair.snk MyContainer  
```  
  
 El comando siguiente extrae la clave pública de `keyPair.snk` y la almacena en `publicKey.snk`.  
  
```console  
sn -p keyPair.snk publicKey.snk  
```  
  
 El siguiente comando muestra la clave pública y el token para la clave pública incluida en `publicKey.snk`.  
  
```console  
sn -tp publicKey.snk  
```  
  
 El comando siguiente comprueba el ensamblado `MyAsm.dll`.  
  
```console  
sn -v MyAsm.dll  
```  
  
 El comando siguiente elimina `MyContainer` del CSP predeterminado.  
  
```console  
sn -d MyContainer  
```  
  
## <a name="see-also"></a>Vea también

- [Herramientas](index.md)
- [Al.exe (Assembly Linker)](al-exe-assembly-linker.md)
- [Ensamblados con nombre seguro](../../standard/assembly/strong-named.md)
- [Shells de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell)
