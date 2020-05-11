---
title: API no admitidas en .NET Core
titleSuffix: ''
description: Obtenga información sobre qué API de .NET Framework siempre producen una excepción en .NET Core.
ms.date: 12/23/2019
ms.openlocfilehash: 941e9149c7679afe4a888149108d0a9a28e5e7ab
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82794603"
---
# <a name="apis-that-always-throw-exceptions-on-net-core"></a><span data-ttu-id="15544-103">API que siempre producen excepciones en .NET Core</span><span class="sxs-lookup"><span data-stu-id="15544-103">APIs that always throw exceptions on .NET Core</span></span>

<span data-ttu-id="15544-104">Las siguientes API siempre producirán una <xref:System.PlatformNotSupportedException> en .NET Core en todas las plataformas, o bien en un subconjunto de estas.</span><span class="sxs-lookup"><span data-stu-id="15544-104">The following APIs will always throw a <xref:System.PlatformNotSupportedException> on .NET Core on all or a subset of platforms.</span></span>

<span data-ttu-id="15544-105">En este artículo se organizan los miembros de API afectados por el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="15544-105">This article organizes the affected API members by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="15544-106">Este artículo sigue en desarrollo.</span><span class="sxs-lookup"><span data-stu-id="15544-106">This article is a work-in-progress.</span></span> <span data-ttu-id="15544-107">No es una lista completa de las API que producen excepciones en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="15544-107">It is not a complete list of APIs that throw exceptions on .NET Core.</span></span>
> - <span data-ttu-id="15544-108">En este artículo no se incluyen las implementaciones de interfaz explícitas para la serialización binaria que se inician en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="15544-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET Core.</span></span> <span data-ttu-id="15544-109">Para obtener más información, vea [Serialización binaria en .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span><span class="sxs-lookup"><span data-stu-id="15544-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="15544-110">Sistema</span><span class="sxs-lookup"><span data-stu-id="15544-110">System</span></span>

| <span data-ttu-id="15544-111">Member</span><span class="sxs-lookup"><span data-stu-id="15544-111">Member</span></span> | <span data-ttu-id="15544-112">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-112">Platforms that throw</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="15544-113">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="15544-114">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="15544-115">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="15544-116">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="15544-117">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="15544-118">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="15544-119">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="15544-120">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="15544-121">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="15544-122">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="15544-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="15544-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="15544-124">Member</span><span class="sxs-lookup"><span data-stu-id="15544-124">Member</span></span> | <span data-ttu-id="15544-125">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-125">Platforms that throw</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="15544-126">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="15544-127">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="15544-128">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="15544-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="15544-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="15544-130">Member</span><span class="sxs-lookup"><span data-stu-id="15544-130">Member</span></span> | <span data-ttu-id="15544-131">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-131">Platforms that throw</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="15544-132">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="15544-133">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="15544-134">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="15544-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="15544-135">System.Configuration</span></span>

| <span data-ttu-id="15544-136">Member</span><span class="sxs-lookup"><span data-stu-id="15544-136">Member</span></span> | <span data-ttu-id="15544-137">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-137">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="15544-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (todos los miembros)</span><span class="sxs-lookup"><span data-stu-id="15544-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="15544-139">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="15544-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="15544-140">System.Console</span></span>

| <span data-ttu-id="15544-141">Member</span><span class="sxs-lookup"><span data-stu-id="15544-141">Member</span></span> | <span data-ttu-id="15544-142">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-142">Platforms that throw</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="15544-143">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-143">Linux and macOS</span></span> |
| <span data-ttu-id="15544-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="15544-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="15544-145">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-145">Linux and macOS</span></span> |
| <span data-ttu-id="15544-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="15544-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="15544-147">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-147">Linux and macOS</span></span> |
| <span data-ttu-id="15544-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="15544-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="15544-149">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-149">Linux and macOS</span></span> |
| <span data-ttu-id="15544-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (solo Obtener)</span><span class="sxs-lookup"><span data-stu-id="15544-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="15544-151">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="15544-152">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="15544-153">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="15544-154">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-154">Linux and macOS</span></span> |
| <span data-ttu-id="15544-155"><xref:System.Console.Title?displayProperty=nameWithType> (solo Obtener)</span><span class="sxs-lookup"><span data-stu-id="15544-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="15544-156">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-156">Linux and macOS</span></span> |
| <span data-ttu-id="15544-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="15544-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="15544-158">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-158">Linux and macOS</span></span> |
| <span data-ttu-id="15544-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="15544-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="15544-160">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-160">Linux and macOS</span></span> |
| <span data-ttu-id="15544-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="15544-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="15544-162">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-162">Linux and macOS</span></span> |
| <span data-ttu-id="15544-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="15544-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="15544-164">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="15544-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="15544-165">System.Data.Common</span></span>

| <span data-ttu-id="15544-166">Member</span><span class="sxs-lookup"><span data-stu-id="15544-166">Member</span></span> | <span data-ttu-id="15544-167">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-167">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="15544-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (genera <xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="15544-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="15544-169">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="15544-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="15544-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="15544-171">Member</span><span class="sxs-lookup"><span data-stu-id="15544-171">Member</span></span> | <span data-ttu-id="15544-172">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-172">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="15544-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="15544-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="15544-174">Linux</span><span class="sxs-lookup"><span data-stu-id="15544-174">Linux</span></span> |
| <span data-ttu-id="15544-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="15544-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="15544-176">Linux</span><span class="sxs-lookup"><span data-stu-id="15544-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="15544-177">macOS</span><span class="sxs-lookup"><span data-stu-id="15544-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="15544-178">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | <span data-ttu-id="15544-179">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="15544-180">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="15544-181">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="15544-182">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="15544-183">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-183">Linux and macOS</span></span> |
| <span data-ttu-id="15544-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="15544-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="15544-185">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-185">Linux and macOS</span></span> |
| <span data-ttu-id="15544-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (solo Obtener)</span><span class="sxs-lookup"><span data-stu-id="15544-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="15544-187">macOS</span><span class="sxs-lookup"><span data-stu-id="15544-187">macOS</span></span> |
| <span data-ttu-id="15544-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="15544-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="15544-189">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-189">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="15544-190">System.IO</span><span class="sxs-lookup"><span data-stu-id="15544-190">System.IO</span></span>

| <span data-ttu-id="15544-191">Member</span><span class="sxs-lookup"><span data-stu-id="15544-191">Member</span></span> | <span data-ttu-id="15544-192">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-192">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="15544-193">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-193">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="15544-194">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-194">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="15544-195">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="15544-195">System.IO.Pipes</span></span>

| <span data-ttu-id="15544-196">Member</span><span class="sxs-lookup"><span data-stu-id="15544-196">Member</span></span> | <span data-ttu-id="15544-197">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-197">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="15544-198">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-198">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="15544-199">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="15544-200">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="15544-201">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-201">Linux and macOS</span></span> |
| <span data-ttu-id="15544-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="15544-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="15544-203">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-203">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="15544-204">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-204">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="15544-205">System.Media</span><span class="sxs-lookup"><span data-stu-id="15544-205">System.Media</span></span>

| <span data-ttu-id="15544-206">Member</span><span class="sxs-lookup"><span data-stu-id="15544-206">Member</span></span> | <span data-ttu-id="15544-207">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-207">Platforms that throw</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="15544-208">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-208">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="15544-209">System.Net</span><span class="sxs-lookup"><span data-stu-id="15544-209">System.Net</span></span>

| <span data-ttu-id="15544-210">Member</span><span class="sxs-lookup"><span data-stu-id="15544-210">Member</span></span> | <span data-ttu-id="15544-211">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-211">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="15544-212">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-212">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="15544-213">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-213">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="15544-214">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-214">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="15544-215">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-215">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="15544-216">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-216">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="15544-217">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-217">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="15544-218">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="15544-219">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-219">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="15544-220">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="15544-221">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-221">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="15544-222">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-222">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="15544-223">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-223">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="15544-224">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-224">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="15544-225">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-225">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="15544-226">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-226">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="15544-227">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-227">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="15544-228">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-228">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="15544-229">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="15544-229">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="15544-230">Member</span><span class="sxs-lookup"><span data-stu-id="15544-230">Member</span></span> | <span data-ttu-id="15544-231">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-231">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="15544-232">Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="15544-232">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="15544-233">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="15544-233">System.Net.Sockets</span></span>

| <span data-ttu-id="15544-234">Member</span><span class="sxs-lookup"><span data-stu-id="15544-234">Member</span></span> | <span data-ttu-id="15544-235">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-235">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.%23ctor(System.Net.Sockets.SocketInformation)> | <span data-ttu-id="15544-236">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-236">All</span></span> |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="15544-237">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-237">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="15544-238">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="15544-238">System.Net.WebSockets</span></span>

| <span data-ttu-id="15544-239">Member</span><span class="sxs-lookup"><span data-stu-id="15544-239">Member</span></span> | <span data-ttu-id="15544-240">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-240">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="15544-241">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-241">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="15544-242">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="15544-242">System.Reflection</span></span>

| <span data-ttu-id="15544-243">Member</span><span class="sxs-lookup"><span data-stu-id="15544-243">Member</span></span> | <span data-ttu-id="15544-244">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-244">Platforms that throw</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="15544-245">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-245">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="15544-246">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-246">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="15544-247">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-247">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="15544-248">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-248">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)> | <span data-ttu-id="15544-249">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="15544-250">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-250">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="15544-251">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-251">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="15544-252">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="15544-252">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="15544-253">Member</span><span class="sxs-lookup"><span data-stu-id="15544-253">Member</span></span> | <span data-ttu-id="15544-254">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-254">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="15544-255">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-255">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="15544-256">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="15544-256">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="15544-257">Member</span><span class="sxs-lookup"><span data-stu-id="15544-257">Member</span></span> | <span data-ttu-id="15544-258">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-258">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="15544-259">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-259">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="15544-260">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="15544-261">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-261">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="15544-262">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-262">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="15544-263">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-263">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="15544-264">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-264">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="15544-265">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-265">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="15544-266">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="15544-266">System.Runtime.Serialization</span></span>

| <span data-ttu-id="15544-267">Member</span><span class="sxs-lookup"><span data-stu-id="15544-267">Member</span></span> | <span data-ttu-id="15544-268">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-268">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="15544-269">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-269">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="15544-270">System.Security</span><span class="sxs-lookup"><span data-stu-id="15544-270">System.Security</span></span>

| <span data-ttu-id="15544-271">Member</span><span class="sxs-lookup"><span data-stu-id="15544-271">Member</span></span> | <span data-ttu-id="15544-272">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-272">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="15544-273">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-273">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="15544-274">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-274">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="15544-275">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-275">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="15544-276">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-276">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="15544-277">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-277">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="15544-278">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-278">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="15544-279">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-279">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="15544-280">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-280">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="15544-281">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-281">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="15544-282">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-282">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="15544-283">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-283">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="15544-284">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-284">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="15544-285">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-285">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="15544-286">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-286">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="15544-287">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="15544-287">System.Security.Claims</span></span>

| <span data-ttu-id="15544-288">Member</span><span class="sxs-lookup"><span data-stu-id="15544-288">Member</span></span> | <span data-ttu-id="15544-289">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-289">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor> | <span data-ttu-id="15544-290">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-290">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="15544-291">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)> | <span data-ttu-id="15544-292">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="15544-293">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-293">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="15544-294">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-294">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="15544-295">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="15544-295">System.Security.Cryptography</span></span>

| <span data-ttu-id="15544-296">Member</span><span class="sxs-lookup"><span data-stu-id="15544-296">Member</span></span> | <span data-ttu-id="15544-297">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-297">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="15544-298">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-298">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A> | <span data-ttu-id="15544-299">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-299">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="15544-300">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="15544-301">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="15544-302">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="15544-303">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="15544-304">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="15544-305">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="15544-306">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="15544-307">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="15544-308">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="15544-309">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="15544-310">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="15544-311">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-311">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="15544-312">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-312">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="15544-313">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="15544-314">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="15544-315">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="15544-316">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="15544-317">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-317">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="15544-318">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="15544-319">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-319">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="15544-320">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-320">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="15544-321">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="15544-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="15544-322">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-322">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="15544-323">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-323">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="15544-324">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="15544-325">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-325">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="15544-326">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="15544-326">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="15544-327">Member</span><span class="sxs-lookup"><span data-stu-id="15544-327">Member</span></span> | <span data-ttu-id="15544-328">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-328">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)> | <span data-ttu-id="15544-329">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-329">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="15544-330">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-330">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="15544-331">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-331">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="15544-332">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="15544-332">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="15544-333">Member</span><span class="sxs-lookup"><span data-stu-id="15544-333">Member</span></span> | <span data-ttu-id="15544-334">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-334">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="15544-335">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="15544-336">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-336">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="15544-337">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-337">All</span></span> |
| <span data-ttu-id="15544-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="15544-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="15544-339">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-339">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="15544-340">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="15544-340">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="15544-341">Member</span><span class="sxs-lookup"><span data-stu-id="15544-341">Member</span></span> | <span data-ttu-id="15544-342">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-342">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="15544-343">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-343">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="15544-344">System.Security.Policy</span><span class="sxs-lookup"><span data-stu-id="15544-344">System.Security.Policy</span></span>

| <span data-ttu-id="15544-345">Member</span><span class="sxs-lookup"><span data-stu-id="15544-345">Member</span></span> | <span data-ttu-id="15544-346">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-346">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="15544-347">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-347">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="15544-348">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="15544-348">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="15544-349">Member</span><span class="sxs-lookup"><span data-stu-id="15544-349">Member</span></span> | <span data-ttu-id="15544-350">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-350">Platforms that throw</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="15544-351">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-351">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="15544-352">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="15544-352">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="15544-353">Member</span><span class="sxs-lookup"><span data-stu-id="15544-353">Member</span></span> | <span data-ttu-id="15544-354">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-354">Platforms that throw</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="15544-355">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-355">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="15544-356">System.Threading</span><span class="sxs-lookup"><span data-stu-id="15544-356">System.Threading</span></span>

| <span data-ttu-id="15544-357">Member</span><span class="sxs-lookup"><span data-stu-id="15544-357">Member</span></span> | <span data-ttu-id="15544-358">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-358">Platforms that throw</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="15544-359">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-359">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="15544-360">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-360">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="15544-361">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-361">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="15544-362">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-362">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="15544-363">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-363">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="15544-364">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-364">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="15544-365">System.Xml</span><span class="sxs-lookup"><span data-stu-id="15544-365">System.Xml</span></span>

| <span data-ttu-id="15544-366">Member</span><span class="sxs-lookup"><span data-stu-id="15544-366">Member</span></span> | <span data-ttu-id="15544-367">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="15544-367">Platforms that throw</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="15544-368">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="15544-369">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-369">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="15544-370">Todas</span><span class="sxs-lookup"><span data-stu-id="15544-370">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="15544-371">Vea también</span><span class="sxs-lookup"><span data-stu-id="15544-371">See also</span></span>

- [<span data-ttu-id="15544-372">Cambios importantes para la migración desde .NET Framework a .NET Core</span><span class="sxs-lookup"><span data-stu-id="15544-372">Breaking changes for migration from .NET Framework to .NET Core</span></span>](fx-core.md)
- [<span data-ttu-id="15544-373">Serialización binaria en .NET Core</span><span class="sxs-lookup"><span data-stu-id="15544-373">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- [<span data-ttu-id="15544-374">Analizador de portabilidad de .NET</span><span class="sxs-lookup"><span data-stu-id="15544-374">.NET portability analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
