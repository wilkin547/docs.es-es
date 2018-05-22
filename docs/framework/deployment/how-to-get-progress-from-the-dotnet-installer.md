---
title: 'Cómo: Obtener el progreso del instalador de .NET Framework 4.5'
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- progress information, .NET Framework installer
- .NET Framework, installing
ms.assetid: 0a1a3ba3-7e46-4df2-afd3-f3a8237e1c4f
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 84bd96f27e8276546bef0dd9994163ccd843ac20
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-get-progress-from-the-net-framework-45-installer"></a><span data-ttu-id="7d1e8-102">Cómo: Obtener el progreso del instalador de .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="7d1e8-102">How to: Get Progress from the .NET Framework 4.5 Installer</span></span>
<span data-ttu-id="7d1e8-103">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] es un runtime redistribuible.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-103">The [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] is a redistributable runtime.</span></span> <span data-ttu-id="7d1e8-104">Si desarrolla aplicaciones para esta versión de .NET Framework, puede incluir (encadenar) el programa de instalación de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] como un requisito previo para la instalación de su aplicación.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-104">If you develop apps for this version of the .NET Framework, you can include (chain) [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] setup as a prerequisite part of your app's setup.</span></span> <span data-ttu-id="7d1e8-105">Para presentar al usuario una experiencia de instalación personalizada o unificada, tal vez desee iniciar silenciosamente el proceso de instalación de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] y realizar su seguimiento mientras se muestra el progreso de la instalación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-105">To present a customized or unified setup experience, you may want to silently launch [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] setup and track its progress while showing your app's setup progress.</span></span> <span data-ttu-id="7d1e8-106">Para habilitar el seguimiento silencioso, el programa de instalación de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] (que se puede observar) define un protocolo mediante el uso de un segmento de E/S (MMIO) asignado a la memoria para comunicarse con el programa de instalación (el proceso observador o encadenador).</span><span class="sxs-lookup"><span data-stu-id="7d1e8-106">To enable silent tracking, [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] setup (which can be watched) defines a protocol by using a memory-mapped I/O (MMIO) segment to communicate with your setup (the watcher or chainer).</span></span> <span data-ttu-id="7d1e8-107">Este protocolo proporciona al encadenador una manera de obtener información de progreso, conseguir resultados detallados, responder a mensajes y cancelar el programa de instalación de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d1e8-107">This protocol defines a way for a chainer to obtain progress information, get detailed results, respond to messages, and cancel the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] setup.</span></span>  
  
-   <span data-ttu-id="7d1e8-108">**Invocación**.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-108">**Invocation** .</span></span>  <span data-ttu-id="7d1e8-109">Para llamar al programa de instalación de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] y recibir información sobre el progreso de la sección MMIO, el programa de instalación debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7d1e8-109">To call [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] setup and receive progress information from the MMIO section, your setup program must do the following:</span></span>  
  
    1.  <span data-ttu-id="7d1e8-110">Llamar al programa redistribuible de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="7d1e8-110">Call the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]redistributable program:</span></span>  
  
        ```  
        dotNetFx45_Full_x86_x64.exe /q /norestart /pipe section-name  
        ```  
  
         <span data-ttu-id="7d1e8-111">donde *section name* es cualquier nombre que quiera usar para identificar a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-111">where *section name* is any name you want to use to identify your app.</span></span> <span data-ttu-id="7d1e8-112">El programa de instalación de .NET Framework realiza operaciones asincrónicas de lectura y escritura en la sección MMIO, de modo que tal vez encuentre conveniente usar eventos y mensajes durante ese periodo.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-112">.NET Framework setup reads and writes to the MMIO section asynchronously, so you might find it convenient to use events and messages during that time.</span></span> <span data-ttu-id="7d1e8-113">En el ejemplo, el proceso del programa de instalación de .NET Framework lo crea un constructor que asigna la sección MMIO (`TheSectionName`) y define un evento (`TheEventName`):</span><span class="sxs-lookup"><span data-stu-id="7d1e8-113">In the example, the .NET Framework setup process is created by a constructor that both allocates the MMIO section (`TheSectionName`) and defines an event (`TheEventName`):</span></span>  
  
        ```  
        Server():ChainerSample::MmioChainer(L"TheSectionName", L"TheEventName")  
        ```  
  
         <span data-ttu-id="7d1e8-114">Sustituya esos nombres por nombres que sean únicos en su programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-114">Please replace those names with names that are unique to your setup program.</span></span>  
  
    2.  <span data-ttu-id="7d1e8-115">Leer la sección MMIO.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-115">Read from the MMIO section.</span></span> <span data-ttu-id="7d1e8-116">En [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], las operaciones de descarga e instalación son simultáneas: una parte de .NET Framework puede estar instalándose mientras otra se descarga.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-116">In the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], the download and installation operations are simultaneous: One part of the .NET Framework might be installing while another part is downloading.</span></span> <span data-ttu-id="7d1e8-117">Por tanto, el progreso se devuelve (es decir, se escribe) en la sección MMIO como dos números (`m_downloadSoFar` y `m_installSoFar`) que van subiendo desde 0 hasta 255.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-117">As a result, progress is sent back (that is, written) to the MMIO section as two numbers (`m_downloadSoFar` and `m_installSoFar`) that increase from 0 to 255.</span></span> <span data-ttu-id="7d1e8-118">Cuando se escribe 255 y .NET Framework se cierra, la instalación se completa.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-118">When 255 is written and the .NET Framework exits, the installation is complete.</span></span>  
  
-   <span data-ttu-id="7d1e8-119">**Códigos de salida**.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-119">**Exit codes**.</span></span> <span data-ttu-id="7d1e8-120">Los códigos de salida siguientes que proceden del comando que llama al programa redistribuible de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] indican si la instalación se ha realizado correctamente o no:</span><span class="sxs-lookup"><span data-stu-id="7d1e8-120">The following exit codes from the command to call the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] redistributable program indicate whether setup has succeeded or failed:</span></span>  
  
    -   <span data-ttu-id="7d1e8-121">0: la instalación se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-121">0 - Setup completed successfully.</span></span>  
  
    -   <span data-ttu-id="7d1e8-122">3010: el programa de instalación se completó correctamente; es necesario reiniciar el sistema.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-122">3010 – Setup completed successfully; a system restart is required.</span></span>  
  
    -   <span data-ttu-id="7d1e8-123">1602: se ha cancelado la instalación.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-123">1602 – Setup has been canceled.</span></span>  
  
    -   <span data-ttu-id="7d1e8-124">Todos los demás códigos: se han producido errores en la instalación. Consulte los archivos de registro creados en %temp% para ver los detalles.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-124">All other codes - Setup encountered errors; examine the log files created in %temp% for details.</span></span>  
  
-   <span data-ttu-id="7d1e8-125">**Cancelación de la instalación**.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-125">**Canceling setup**.</span></span> <span data-ttu-id="7d1e8-126">Puede cancelar la instalación en cualquier momento utilizando el método `Abort` para establecer las marcas `m_downloadAbort` y `m_ installAbort` en la sección MMIO.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-126">You can cancel setup at any time by using the `Abort` method to set the `m_downloadAbort` and `m_ installAbort` flags in the MMIO section.</span></span>  
  
## <a name="chainer-sample"></a><span data-ttu-id="7d1e8-127">Ejemplo de encadenador</span><span class="sxs-lookup"><span data-stu-id="7d1e8-127">Chainer Sample</span></span>  
 <span data-ttu-id="7d1e8-128">El ejemplo de encadenador inicia de forma silenciosa el programa de instalación de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] y realiza un seguimiento de este mientras se muestra el progreso.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-128">The Chainer sample silently launches and tracks [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] setup while showing progress.</span></span> <span data-ttu-id="7d1e8-129">Este ejemplo es similar al ejemplo de encadenador proporcionado para .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-129">This sample is similar to the Chainer sample provided for the .NET Framework 4.</span></span> <span data-ttu-id="7d1e8-130">Sin embargo, también puede evitar reinicios del sistema procesando el cuadro de mensaje para cerrar las aplicaciones de .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-130">However, in addition, it can avoid system restarts by processing the message box for closing .NET Framework 4 apps.</span></span> <span data-ttu-id="7d1e8-131">Para más información sobre este cuadro de mensaje, vea [Reducing System Restarts During .NET Framework 4.5 Installations](../../../docs/framework/deployment/reducing-system-restarts.md) (Reducir los reinicios del sistema durante las instalaciones de .NET Framework 4.5).</span><span class="sxs-lookup"><span data-stu-id="7d1e8-131">For information about this message box, see [Reducing System Restarts During .NET Framework 4.5 Installations](../../../docs/framework/deployment/reducing-system-restarts.md).</span></span> <span data-ttu-id="7d1e8-132">Puede usar este ejemplo con el programa de instalación de .NET Framework 4; en ese caso, el mensaje simplemente no se envía.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-132">You can use this sample with the .NET Framework 4 installer; in that scenario, the message is simply not sent.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="7d1e8-133">Debe ejecutar el ejemplo como administrador.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-133">You must run the example as an administrator.</span></span>  
  
 <span data-ttu-id="7d1e8-134">Puede descargar la solución completa de Visual Studio del [ejemplo de encadenador para .NET Framework 4.5](http://go.microsoft.com/fwlink/?LinkId=231345) en la galería de ejemplos de MSDN.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-134">You can download the complete Visual Studio solution for the [.NET Framework 4.5 Chainer Sample](http://go.microsoft.com/fwlink/?LinkId=231345) from the MSDN Samples Gallery.</span></span>  
  
 <span data-ttu-id="7d1e8-135">Las secciones siguientes describen los archivos importantes en este ejemplo: MMIOChainer.h, ChainingdotNet4.cpp e IProgressObserver.h.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-135">The following sections describe the significant files in this sample: MMIOChainer.h, ChainingdotNet4.cpp, and IProgressObserver.h.</span></span>  
  
#### <a name="mmiochainerh"></a><span data-ttu-id="7d1e8-136">MMIOChainer.h</span><span class="sxs-lookup"><span data-stu-id="7d1e8-136">MMIOChainer.h</span></span>  
  
-   <span data-ttu-id="7d1e8-137">El archivo MMIOChainer.h (vea el [código completo](http://go.microsoft.com/fwlink/?LinkId=231369)) contiene la definición de la estructura de datos y la clase base de la que debería derivarse la clase del encadenador.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-137">The MMIOChainer.h file (see [complete code](http://go.microsoft.com/fwlink/?LinkId=231369)) contains the data structure definition and the base class from which the chainer class should be derived.</span></span> <span data-ttu-id="7d1e8-138">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] amplía la estructura de datos MMIO para controlar los datos que necesita el instalador de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d1e8-138">The [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] extends the MMIO data structure to handle data that the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] installer needs.</span></span> <span data-ttu-id="7d1e8-139">Los cambios en la estructura MMIO son compatible con versiones anteriores, por lo que un encadenador de .NET Framework 4 puede trabajar con el programa de instalación de .NET Framework 4.5 sin necesidad de volver a compilar.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-139">The changes to the MMIO structure are backward-compatible, so a .NET Framework 4 chainer can work with .NET Framework 4.5 setup without requiring recompilation.</span></span> <span data-ttu-id="7d1e8-140">Sin embargo, este escenario no es compatible con la característica para reducir los reinicios del sistema.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-140">However, this scenario does not support the feature for reducing system restarts.</span></span>  
  
     <span data-ttu-id="7d1e8-141">Un campo de versión proporciona un medio de identificar las revisiones para la estructura y el formato de mensajes.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-141">A version field provides a means of identifying revisions to the structure and message format.</span></span>  <span data-ttu-id="7d1e8-142">El programa de instalación de .NET Framework determina la versión de la interfaz del encadenador llamando a la función `VirtualQuery` para averiguar el tamaño de la asignación del archivo.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-142">The .NET Framework setup determines the version of the chainer interface by calling the `VirtualQuery` function to determine the size of the file mapping.</span></span>  <span data-ttu-id="7d1e8-143">Si el tamaño es lo suficientemente grande para acomodar el campo de versión, el programa de instalación de .NET Framework utiliza el valor especificado.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-143">If the size is large enough to accommodate the version field, .NET Framework setup uses the specified value.</span></span> <span data-ttu-id="7d1e8-144">Si la asignación del archivo es demasiado pequeña para contener un campo de versión, que es lo que sucede con .NET Framework 4, el proceso de instalación asume que es la versión 0 (4).</span><span class="sxs-lookup"><span data-stu-id="7d1e8-144">If the file mapping is too small to contain a version field, which is the case with the .NET Framework 4, the setup process assumes version 0 (4).</span></span> <span data-ttu-id="7d1e8-145">Si el encadenador no admite la versión del mensaje que el programa de instalación de .NET Framework desea enviar, este asume que la respuesta es ignorar.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-145">If the chainer does not support the version of the message that .NET Framework setup wants to send, .NET Framework setup assumes an ignore response.</span></span>  
  
     <span data-ttu-id="7d1e8-146">La estructura de datos MMIO se define como sigue:</span><span class="sxs-lookup"><span data-stu-id="7d1e8-146">The MMIO data structure is defined as follows:</span></span>  
  
    ```cpp  
    // MMIO data structure for interprocess communication  
        struct MmioDataStructure  
        {  
            bool m_downloadFinished;               // Is download complete?  
            bool m_installFinished;                // Is installation complete?  
            bool m_downloadAbort;                  // Set to cause downloader to abort.  
            bool m_installAbort;                   // Set to cause installer to abort.  
            HRESULT m_hrDownloadFinished;          // Resulting HRESULT for download.  
            HRESULT m_hrInstallFinished;           // Resulting HRESULT for installation.  
            HRESULT m_hrInternalError;  
            WCHAR m_szCurrentItemStep[MAX_PATH];  
            unsigned char m_downloadSoFar;         // Download progress 0-255 (0-100% done).   
            unsigned char m_installSoFar;          // Installation progress 0-255 (0-100% done).  
            WCHAR m_szEventName[MAX_PATH];         // Event that chainer creates and chainee opens to sync communications.  
  
            BYTE m_version;                        // Version of the data structure, set by chainer:  
                                                   // 0x0: .NET Framework 4   
                                                   // 0x1: .NET Framework 4.5  
  
            DWORD m_messageCode;                   // Current message sent by the chainee; 0 if no message is active.  
            DWORD m_messageResponse;               // Chainer's response to current message; 0 if not yet handled.  
            DWORD m_messageDataLength;             // Length of the m_messageData field, in bytes.  
            BYTE m_messageData[1];                 // Variable-length buffer; content depends on m_messageCode.  
        };  
    ```  
  
-   <span data-ttu-id="7d1e8-147">La estructura de datos `MmioDataStructure` no debe utilizarse directamente; use la clase `MmioChainer` en su lugar para implementar el encadenador.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-147">The `MmioDataStructure` data structure should not be used directly; use the `MmioChainer` class instead to implement your chainer.</span></span> <span data-ttu-id="7d1e8-148">Derive a partir de la clase `MmioChainer` para encadenar el paquete redistribuible de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d1e8-148">Derive from the `MmioChainer` class to chain the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] redistributable.</span></span>  
  
#### <a name="iprogressobserverh"></a><span data-ttu-id="7d1e8-149">IProgressObserver.h</span><span class="sxs-lookup"><span data-stu-id="7d1e8-149">IProgressObserver.h</span></span>  
  
-   <span data-ttu-id="7d1e8-150">El archivo IProgressObserver.h implementa un observador de progreso ([vea el código completo](http://go.microsoft.com/fwlink/?LinkId=231370)).</span><span class="sxs-lookup"><span data-stu-id="7d1e8-150">The IProgressObserver.h file implements a progress observer ([see complete code](http://go.microsoft.com/fwlink/?LinkId=231370)).</span></span> <span data-ttu-id="7d1e8-151">Este observador recibe notificaciones del progreso de descarga e instalación (se especifica como un `char` sin firmar, 0-255, que indica 1-100 % completado).</span><span class="sxs-lookup"><span data-stu-id="7d1e8-151">This observer gets notified of download and installation progress (specified as an unsigned `char`, 0-255, indicating 1%-100% complete).</span></span> <span data-ttu-id="7d1e8-152">El observador también recibe una notificación cuando el objeto encadenado envía un mensaje y debe enviar una respuesta.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-152">The observer is also notified when the chainee sends a message, and the observer should send a response.</span></span>  
  
    ```cpp  
        class IProgressObserver  
        {  
        public:  
            virtual void OnProgress(unsigned char) = 0; // 0 - 255:  255 == 100%  
            virtual void Finished(HRESULT) = 0;         // Called when operation is complete    
            virtual DWORD Send(DWORD dwMessage, LPVOID pData, DWORD dwDataLength) = 0; // Called when a message is sent  
        };  
    ```  
  
#### <a name="chainingdotnet45cpp"></a><span data-ttu-id="7d1e8-153">ChainingdotNet4.5.cpp</span><span class="sxs-lookup"><span data-stu-id="7d1e8-153">ChainingdotNet4.5.cpp</span></span>  
  
-   <span data-ttu-id="7d1e8-154">El archivo [ChainingdotNet4.5.cpp](http://go.microsoft.com/fwlink/?LinkId=231368) implementa la clase `Server`, que deriva de la clase `MmioChainer` e invalida los métodos adecuados para mostrar la información de progreso.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-154">The [ChainingdotNet4.5.cpp](http://go.microsoft.com/fwlink/?LinkId=231368) file implements the `Server` class, which derives from the `MmioChainer` class and overrides the appropriate methods to display progress information.</span></span> <span data-ttu-id="7d1e8-155">El MmioChainer crea una sección con el nombre de la sección especificada e inicializa al encadenador con el nombre de evento especificado.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-155">The MmioChainer creates a section with the specified section name and initializes the chainer with the specified event name.</span></span> <span data-ttu-id="7d1e8-156">El nombre del evento se guarda en la estructura de datos asignada.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-156">The event name is saved in the mapped data structure.</span></span> <span data-ttu-id="7d1e8-157">Los nombres de sección y de evento deben ser únicos.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-157">You should make the section and event names unique.</span></span> <span data-ttu-id="7d1e8-158">La clase `Server` del código siguiente inicia el programa de instalación especificado, supervisa su progreso y devuelve un código de salida.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-158">The `Server` class in the following code launches the specified setup program, monitors its progress, and returns an exit code.</span></span>  
  
    ```cpp  
    class Server : public ChainerSample::MmioChainer, public ChainerSample::IProgressObserver  
    {  
    public:  
        …………….  
        Server():ChainerSample::MmioChainer(L"TheSectionName", L"TheEventName") //customize for your event names  
        {}  
    ```  
  
     <span data-ttu-id="7d1e8-159">La instalación se inicia en el método Main.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-159">The installation is started in the Main method.</span></span>  
  
    ```cpp  
    // Main entry point for program  
    int __cdecl main(int argc, _In_count_(argc) char **_argv)  
    {  
        int result = 0;  
        CString args;  
        if (argc > 1)  
        {  
            args = CString(_argv[1]);  
        }  
  
        if (IsNetFx4Present(NETFX45_RC_REVISION))  
        {  
            printf(".NET Framework 4.5 is already installed");  
        }  
        else  
        {  
            result = Server().Launch(args);  
        }  
  
        return result;  
    }  
    ```  
  
-   <span data-ttu-id="7d1e8-160">Antes de iniciar la instalación, el encadenador comprueba si [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] ya está instalado mediante una llamada a `IsNetFx4Present`:</span><span class="sxs-lookup"><span data-stu-id="7d1e8-160">Before launching the installation, the chainer checks to see if the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] is already installed by calling `IsNetFx4Present`:</span></span>  
  
    ```cpp  
    ///  Checks for presence of the .NET Framework 4.  
    ///    A value of 0 for dwMinimumRelease indicates a check for the .NET Framework 4 full  
    ///    Any other value indicates a check for a specific compatible release of the .NET Framework 4.  
    #define NETFX40_FULL_REVISION 0  
    // TODO: Replace with released revision number  
    #define NETFX45_RC_REVISION MAKELONG(50309, 5)   // .NET Framework 4.5   
    bool IsNetFx4Present(DWORD dwMinimumRelease)  
    {  
        DWORD dwError = ERROR_SUCCESS;  
        HKEY hKey = NULL;  
        DWORD dwData = 0;  
        DWORD dwType = 0;  
        DWORD dwSize = sizeof(dwData);  
  
        dwError = ::RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full", 0, KEY_READ, &hKey);  
        if (ERROR_SUCCESS == dwError)  
        {  
            dwError = ::RegQueryValueExW(hKey, L"Release", 0, &dwType, (LPBYTE)&dwData, &dwSize);  
  
            if ((ERROR_SUCCESS == dwError) && (REG_DWORD != dwType))  
            {  
                dwError = ERROR_INVALID_DATA;  
            }  
            else if (ERROR_FILE_NOT_FOUND == dwError)  
            {  
                // Release value was not found, let's check for 4.0.  
                dwError = ::RegQueryValueExW(hKey, L"Install", 0, &dwType, (LPBYTE)&dwData, &dwSize);  
  
                // Install = (REG_DWORD)1;  
                if ((ERROR_SUCCESS == dwError) && (REG_DWORD == dwType) && (dwData == 1))  
                {  
                    // treat 4.0 as Release = 0  
                    dwData = 0;  
                }  
                else  
                {  
                    dwError = ERROR_INVALID_DATA;  
                }  
            }  
        }  
  
        if (hKey != NULL)  
        {  
            ::RegCloseKey(hKey);  
        }  
  
        return ((ERROR_SUCCESS == dwError) && (dwData >= dwMinimumRelease));  
    }  
    ```  
  
-   <span data-ttu-id="7d1e8-161">Puede cambiar la ruta de acceso del archivo ejecutable (Setup.exe en el ejemplo) en el método `Launch` para que apunte a su ubicación correcta o personalizar el código para determinarla.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-161">You can change the path of the executable (Setup.exe in the example) in the `Launch` method to point to its correct location, or customize the code to determine the location.</span></span> <span data-ttu-id="7d1e8-162">La clase base `MmioChainer` proporciona un método `Run()` de bloqueo al que llama la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-162">The `MmioChainer` base class provides a blocking `Run()` method that the derived class calls.</span></span>  
  
    ```cpp  
    bool Launch(const CString& args)  
    {  
    CString cmdline = L"dotNetFx45_Full_x86_x64.exe -pipe TheSectionName " + args; // Customize with name and location of setup .exe that you want to run  
    STARTUPINFO si = {0};  
    si.cb = sizeof(si);  
    PROCESS_INFORMATION pi = {0};  
  
    // Launch the Setup.exe that installs the .NET Framework 4.5  
    BOOL bLaunchedSetup = ::CreateProcess(NULL,   
     cmdline.GetBuffer(),  
     NULL, NULL, FALSE, 0, NULL, NULL,   
     &si,  
     &pi);  
  
    // If successful   
    if (bLaunchedSetup != 0)  
    {  
    IProgressObserver& observer = dynamic_cast<IProgressObserver&>(*this);  
    Run(pi.hProcess, observer);  
  
    ……………………..   
    return (bLaunchedSetup != 0);  
    }  
    ```  
  
-   <span data-ttu-id="7d1e8-163">El método `Send` intercepta y procesa los mensajes.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-163">The `Send` method intercepts and processes the messages.</span></span>  <span data-ttu-id="7d1e8-164">En esta versión de .NET Framework, el único mensaje admitido es el mensaje para cerrar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-164">In this version of the .NET Framework, the only supported message is the close application message.</span></span>  
  
    ```cpp  
            // SendMessage  
            //  
            // Send a message and wait for the response.  
            // dwMessage: Message to send  
            // pData: The buffer to copy the data to  
            // dwDataLength: Initially a pointer to the size of pBuffer.  Upon successful call, the number of bytes copied to pBuffer.  
            //--------------------------------------------------------------  
        virtual DWORD Send(DWORD dwMessage, LPVOID pData, DWORD dwDataLength)  
        {  
            DWORD dwResult = 0;  
            printf("recieved message: %d\n", dwMessage);  
            // Handle message  
            switch (dwMessage)  
            {  
            case MMIO_CLOSE_APPS:  
                {  
                    printf("    applications are holding files in use:\n");  
                    IronMan::MmioCloseApplications* applications = reinterpret_cast<IronMan::MmioCloseApplications*>(pData);  
                    for(DWORD i = 0; i < applications->m_dwApplicationsSize; i++)  
                    {  
                        printf("      %ls (%d)\n", applications->m_applications[i].m_szName, applications->m_applications[i].m_dwPid);  
                    }  
  
                    printf("    should appliations be closed? (Y)es, (N)o, (R)efresh : ");  
                    while (dwResult == 0)  
                    {  
                        switch (toupper(getwchar()))  
                        {  
                        case 'Y':  
                            dwResult = IDYES;  // Close apps  
                            break;  
                        case 'N':  
                            dwResult = IDNO;  
                            break;  
                        case 'R':  
                            dwResult = IDRETRY;  
                            break;  
                        }  
                    }  
                    printf("\n");  
                    break;  
                }  
            default:  
                break;  
            }  
            printf("  response: %d\n  ", dwResult);  
            return dwResult;  
        }  
    };  
    ```  
  
-   <span data-ttu-id="7d1e8-165">Los datos de progreso son un `char` sin signo y estarán comprendidos entre 0 (0 %) y 255 (100 %).</span><span class="sxs-lookup"><span data-stu-id="7d1e8-165">Progress data is an unsigned `char` between 0 (0%) and 255 (100%).</span></span>  
  
    ```cpp  
    private: // IProgressObserver  
        virtual void OnProgress(unsigned char ubProgressSoFar)  
        {…………  
       }  
    ```  
  
-   <span data-ttu-id="7d1e8-166">HRESULT se pasa al método `Finished`.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-166">The HRESULT is passed to the `Finished` method.</span></span>  
  
    ```cpp  
    virtual void Finished(HRESULT hr)  
    {  
    // This HRESULT is communicated over MMIO and may be different than process  
    // Exit code of the Chainee Setup.exe itself  
    printf("\r\nFinished HRESULT: 0x%08X\r\n", hr);  
    }  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="7d1e8-167">El programa redistribuible de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] normalmente escribe muchos mensajes de progreso y un solo mensaje que indica la finalización del proceso (en el lado del encadenador).</span><span class="sxs-lookup"><span data-stu-id="7d1e8-167">The [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] redistributable typically writes many progress messages and a single message that indicates completion (on the chainer side).</span></span> <span data-ttu-id="7d1e8-168">También realiza lecturas asincrónicas en busca de registros `Abort`.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-168">It also reads asynchronously, looking for `Abort` records.</span></span> <span data-ttu-id="7d1e8-169">Si recibe un registro `Abort`, se cancela la instalación y se escribe un registro de finalización usando E_ABORT como datos después que la instalación se ha anulado y las operaciones de instalación se han revertido.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-169">If it receives an `Abort` record, it cancels the installation, and writes a finished record with E_ABORT as its data after the installation has been aborted and setup operations have been rolled back.</span></span>  
  
 <span data-ttu-id="7d1e8-170">Un servidor normal crea un nombre de archivo MMIO aleatorio, crea el archivo (tal y como se muestra en el ejemplo de código anterior, en `Server::CreateSection`) e inicia el programa redistribuible usando el método `CreateProcess` y pasando el nombre de la canalización con la opción `-pipe someFileSectionName`.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-170">A typical server creates a random MMIO file name, creates the file (as shown in the previous code example, in `Server::CreateSection`), and launches the redistributable by using the `CreateProcess` method and passing the pipe name with the `-pipe someFileSectionName` option.</span></span> <span data-ttu-id="7d1e8-171">El servidor debe implementar los métodos `OnProgress`, `Send` y `Finished` con código específico de la interfaz de usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7d1e8-171">The server should implement `OnProgress`, `Send`, and `Finished` methods with application UI-specific code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d1e8-172">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d1e8-172">See Also</span></span>  
 [<span data-ttu-id="7d1e8-173">Guía de implementación para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="7d1e8-173">Deployment Guide for Developers</span></span>](../../../docs/framework/deployment/deployment-guide-for-developers.md)  
 [<span data-ttu-id="7d1e8-174">Implementación</span><span class="sxs-lookup"><span data-stu-id="7d1e8-174">Deployment</span></span>](../../../docs/framework/deployment/index.md)
