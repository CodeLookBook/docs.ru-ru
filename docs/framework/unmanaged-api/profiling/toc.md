# [Профилирование](index.md)
## [Общие сведения о профилировании](profiling-overview.md)
## [Настройка среды профилирования](setting-up-a-profiling-environment.md)
## [Профилировщики CLR и приложения для Магазина Windows](clr-profilers-and-windows-store-apps.md)
## [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md)
## [Интерфейсы профилирования](profiling-interfaces.md)
### [Интерфейс ICLRProfiling](iclrprofiling-interface.md)
#### [Метод AttachProfiler](iclrprofiling-attachprofiler-method.md)
### [Интерфейс ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md)
#### [Метод AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)
### [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
#### [Метод AppDomainCreationFinished](icorprofilercallback-appdomaincreationfinished-method.md)
#### [Метод AppDomainCreationStarted](icorprofilercallback-appdomaincreationstarted-method.md)
#### [Метод AppDomainShutdownFinished](icorprofilercallback-appdomainshutdownfinished-method.md)
#### [Метод AppDomainShutdownStarted](icorprofilercallback-appdomainshutdownstarted-method.md)
#### [Метод AssemblyLoadFinished](icorprofilercallback-assemblyloadfinished-method.md)
#### [Метод AssemblyLoadStarted](icorprofilercallback-assemblyloadstarted-method.md)
#### [Метод AssemblyUnloadFinished](icorprofilercallback-assemblyunloadfinished-method.md)
#### [Метод AssemblyUnloadStarted](icorprofilercallback-assemblyunloadstarted-method.md)
#### [Метод ClassLoadFinished](icorprofilercallback-classloadfinished-method.md)
#### [Метод ClassLoadStarted](icorprofilercallback-classloadstarted-method.md)
#### [Метод ClassUnloadFinished](icorprofilercallback-classunloadfinished-method.md)
#### [Метод ClassUnloadStarted](icorprofilercallback-classunloadstarted-method.md)
#### [Метод COMClassicVTableCreated](icorprofilercallback-comclassicvtablecreated-method.md)
#### [Метод COMClassicVTableDestroyed](icorprofilercallback-comclassicvtabledestroyed-method.md)
#### [Метод ExceptionCatcherEnter](icorprofilercallback-exceptioncatcherenter-method.md)
#### [Метод ExceptionCatcherLeave](icorprofilercallback-exceptioncatcherleave-method.md)
#### [Метод ExceptionCLRCatcherExecute](icorprofilercallback-exceptionclrcatcherexecute-method.md)
#### [Метод ExceptionCLRCatcherFound](icorprofilercallback-exceptionclrcatcherfound-method.md)
#### [Метод ExceptionOSHandlerEnter](icorprofilercallback-exceptionoshandlerenter-method.md)
#### [Метод ExceptionOSHandlerLeave](icorprofilercallback-exceptionoshandlerleave-method.md)
#### [Метод ExceptionSearchCatcherFound](icorprofilercallback-exceptionsearchcatcherfound-method.md)
#### [Метод ExceptionSearchFilterEnter](icorprofilercallback-exceptionsearchfilterenter-method.md)
#### [Метод ExceptionSearchFilterLeave](icorprofilercallback-exceptionsearchfilterleave-method.md)
#### [Метод ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md)
#### [Метод ExceptionSearchFunctionLeave](icorprofilercallback-exceptionsearchfunctionleave-method.md)
#### [Метод ExceptionThrown](icorprofilercallback-exceptionthrown-method.md)
#### [Метод ExceptionUnwindFinallyEnter](icorprofilercallback-exceptionunwindfinallyenter-method.md)
#### [Метод ExceptionUnwindFinallyLeave](icorprofilercallback-exceptionunwindfinallyleave-method.md)
#### [Метод ExceptionUnwindFunctionEnter](icorprofilercallback-exceptionunwindfunctionenter-method.md)
#### [Метод ExceptionUnwindFunctionLeave](icorprofilercallback-exceptionunwindfunctionleave-method.md)
#### [Метод FunctionUnloadStarted](icorprofilercallback-functionunloadstarted-method.md)
#### [Метод Initialize](icorprofilercallback-initialize-method.md)
#### [Метод JITCachedFunctionSearchFinished](icorprofilercallback-jitcachedfunctionsearchfinished-method.md)
#### [Метод JITCachedFunctionSearchStarted](icorprofilercallback-jitcachedfunctionsearchstarted-method.md)
#### [Метод JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md)
#### [Метод JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md)
#### [Метод JITFunctionPitched](icorprofilercallback-jitfunctionpitched-method.md)
#### [Метод JITInlining](icorprofilercallback-jitinlining-method.md)
#### [Метод ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md)
#### [Метод ModuleAttachedToAssembly](icorprofilercallback-moduleattachedtoassembly-method.md)
#### [Метод ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)
#### [Метод ModuleLoadStarted](icorprofilercallback-moduleloadstarted-method.md)
#### [Метод ModuleUnloadFinished](icorprofilercallback-moduleunloadfinished-method.md)
#### [Метод ModuleUnloadStarted](icorprofilercallback-moduleunloadstarted-method.md)
#### [Метод MovedReferences](icorprofilercallback-movedreferences-method.md)
#### [Метод ObjectAllocated](icorprofilercallback-objectallocated-method.md)
#### [Метод ObjectReferences](icorprofilercallback-objectreferences-method.md)
#### [Метод ObjectsAllocatedByClass](icorprofilercallback-objectsallocatedbyclass-method.md)
#### [Метод RemotingClientInvocationFinished](icorprofilercallback-remotingclientinvocationfinished-method.md)
#### [Метод RemotingClientInvocationStarted](icorprofilercallback-remotingclientinvocationstarted-method.md)
#### [Метод RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md)
#### [Метод RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md)
#### [Метод RemotingServerInvocationReturned](icorprofilercallback-remotingserverinvocationreturned-method.md)
#### [Метод RemotingServerInvocationStarted](icorprofilercallback-remotingserverinvocationstarted-method.md)
#### [Метод RemotingServerReceivingMessage](icorprofilercallback-remotingserverreceivingmessage-method.md)
#### [Метод RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md)
#### [Метод RootReferences](icorprofilercallback-rootreferences-method.md)
#### [Метод RuntimeResumeFinished](icorprofilercallback-runtimeresumefinished-method.md)
#### [Метод RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md)
#### [Метод RuntimeSuspendAborted](icorprofilercallback-runtimesuspendaborted-method.md)
#### [Метод RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md)
#### [Метод RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md)
#### [Метод RuntimeThreadResumed](icorprofilercallback-runtimethreadresumed-method.md)
#### [Метод RuntimeThreadSuspended](icorprofilercallback-runtimethreadsuspended-method.md)
#### [Метод Shutdown](icorprofilercallback-shutdown-method.md)
#### [Метод ThreadAssignedToOSThread](icorprofilercallback-threadassignedtoosthread-method.md)
#### [Метод ThreadCreated](icorprofilercallback-threadcreated-method.md)
#### [Метод ThreadDestroyed](icorprofilercallback-threaddestroyed-method.md)
#### [Метод UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md)
### [Интерфейс ICorProfilerCallback2](icorprofilercallback2-interface.md)
#### [Метод FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md)
#### [Метод GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md)
#### [Метод GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md)
#### [Метод HandleCreated](icorprofilercallback2-handlecreated-method.md)
#### [Метод HandleDestroyed](icorprofilercallback2-handledestroyed-method.md)
#### [Метод RootReferences2](icorprofilercallback2-rootreferences2-method.md)
#### [Метод SurvivingReferences](icorprofilercallback2-survivingreferences-method.md)
#### [Метод ThreadNameChanged](icorprofilercallback2-threadnamechanged-method.md)
### [Интерфейс ICorProfilerCallback3](icorprofilercallback3-interface.md)
#### [Метод InitializeForAttach](icorprofilercallback3-initializeforattach-method.md)
#### [Метод ProfilerAttachComplete](icorprofilercallback3-profilerattachcomplete-method.md)
#### [Метод ProfilerDetachSucceeded](icorprofilercallback3-profilerdetachsucceeded-method.md)
### [Интерфейс ICorProfilerCallback4](icorprofilercallback4-interface.md)
#### [Метод GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md)
#### [Метод MovedReferences2](icorprofilercallback4-movedreferences2-method.md)
#### [Метод ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md)
#### [Метод ReJITCompilationStarted](icorprofilercallback4-rejitcompilationstarted-method.md)
#### [Метод ReJITError](icorprofilercallback4-rejiterror-method.md)
#### [Метод SurvivingReferences2](icorprofilercallback4-survivingreferences2-method.md)
### [Интерфейс ICorProfilerCallback5](icorprofilercallback5-interface.md)
#### [Метод ConditionalWeakTableElementReferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md)
### [Интерфейс ICorProfilerCallback6](icorprofilercallback6-interface.md)
#### [Метод GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md)
### [Интерфейс ICorProfilerCallback7](icorprofilercallback7-interface.md)
#### [Метод ModuleInMemorySymbolsUpdated](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)
### [Интерфейс ICorProfilerFunctionControl](icorprofilerfunctioncontrol-interface.md)
#### [Метод SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md)
#### [Метод SetILFunctionBody](icorprofilerfunctioncontrol-setilfunctionbody-method.md)
#### [Метод SetILInstrumentedCodeMap](icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)
### [Интерфейс ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md)
#### [Метод Clone](icorprofilerfunctionenum-clone-method.md)
#### [Метод GetCount](icorprofilerfunctionenum-getcount-method.md)
#### [Метод Next](icorprofilerfunctionenum-next-method.md)
#### [Метод Reset](icorprofilerfunctionenum-reset-method.md)
#### [Метод Skip](icorprofilerfunctionenum-skip-method.md)
### [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
#### [Метод BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md)
#### [Метод EndInprocDebugging](icorprofilerinfo-endinprocdebugging-method.md)
#### [Метод ForceGC](icorprofilerinfo-forcegc-method.md)
#### [Метод GetAppDomainInfo](icorprofilerinfo-getappdomaininfo-method.md)
#### [Метод GetAssemblyInfo](icorprofilerinfo-getassemblyinfo-method.md)
#### [Метод GetClassFromObject](icorprofilerinfo-getclassfromobject-method.md)
#### [Метод GetClassFromToken](icorprofilerinfo-getclassfromtoken-method.md)
#### [Метод GetClassIDInfo](icorprofilerinfo-getclassidinfo-method.md)
#### [Метод GetCodeInfo](icorprofilerinfo-getcodeinfo-method.md)
#### [Метод GetCurrentThreadID](icorprofilerinfo-getcurrentthreadid-method.md)
#### [Метод GetEventMask](icorprofilerinfo-geteventmask-method.md)
#### [Метод GetFunctionFromIP](icorprofilerinfo-getfunctionfromip-method.md)
#### [Метод GetFunctionFromToken](icorprofilerinfo-getfunctionfromtoken-method.md)
#### [Метод GetFunctionInfo](icorprofilerinfo-getfunctioninfo-method.md)
#### [Метод GetHandleFromThread](icorprofilerinfo-gethandlefromthread-method.md)
#### [Метод GetILFunctionBody](icorprofilerinfo-getilfunctionbody-method.md)
#### [Метод GetILFunctionBodyAllocator](icorprofilerinfo-getilfunctionbodyallocator-method.md)
#### [Метод GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md)
#### [Метод GetInprocInspectionInterface](icorprofilerinfo-getinprocinspectioninterface-method.md)
#### [Метод GetInprocInspectionIThisThread](icorprofilerinfo-getinprocinspectionithisthread-method.md)
#### [Метод GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md)
#### [Метод GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md)
#### [Метод GetObjectSize](icorprofilerinfo-getobjectsize-method.md)
#### [Метод GetThreadContext](icorprofilerinfo-getthreadcontext-method.md)
#### [Метод GetThreadInfo](icorprofilerinfo-getthreadinfo-method.md)
#### [Метод GetTokenAndMetadataFromFunction](icorprofilerinfo-gettokenandmetadatafromfunction-method.md)
#### [Метод IsArrayClass](icorprofilerinfo-isarrayclass-method.md)
#### [Метод SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md)
#### [Метод SetEventMask](icorprofilerinfo-seteventmask-method.md)
#### [Метод SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md)
#### [Метод SetFunctionReJIT](icorprofilerinfo-setfunctionrejit-method.md)
#### [Метод SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md)
#### [Метод SetILInstrumentedCodeMap](icorprofilerinfo-setilinstrumentedcodemap-method.md)
### [Интерфейс ICorProfilerInfo2](icorprofilerinfo2-interface.md)
#### [Метод DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md)
#### [Метод EnumModuleFrozenObjects](icorprofilerinfo2-enummodulefrozenobjects-method.md)
#### [Метод GetAppDomainStaticAddress](icorprofilerinfo2-getappdomainstaticaddress-method.md)
#### [Метод GetArrayObjectInfo](icorprofilerinfo2-getarrayobjectinfo-method.md)
#### [Метод GetBoxClassLayout](icorprofilerinfo2-getboxclasslayout-method.md)
#### [Метод GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)
#### [Метод GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md)
#### [Метод GetClassLayout](icorprofilerinfo2-getclasslayout-method.md)
#### [Метод GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md)
#### [Метод GetContextStaticAddress](icorprofilerinfo2-getcontextstaticaddress-method.md)
#### [Метод GetFunctionFromTokenAndTypeArgs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)
#### [Метод GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md)
#### [Метод GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md)
#### [Метод GetNotifiedExceptionClauseInfo](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)
#### [Метод GetObjectGeneration](icorprofilerinfo2-getobjectgeneration-method.md)
#### [Метод GetRVAStaticAddress](icorprofilerinfo2-getrvastaticaddress-method.md)
#### [Метод GetStaticFieldInfo](icorprofilerinfo2-getstaticfieldinfo-method.md)
#### [Метод GetStringLayout](icorprofilerinfo2-getstringlayout-method.md)
#### [Метод GetThreadAppDomain](icorprofilerinfo2-getthreadappdomain-method.md)
#### [Метод GetThreadStaticAddress](icorprofilerinfo2-getthreadstaticaddress-method.md)
#### [Метод SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
### [Интерфейс ICorProfilerInfo3](icorprofilerinfo3-interface.md)
#### [Метод EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md)
#### [Метод EnumModules](icorprofilerinfo3-enummodules-method.md)
#### [Метод GetAppDomainsContainingModule](icorprofilerinfo3-getappdomainscontainingmodule-method.md)
#### [Метод GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md)
#### [Метод GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md)
#### [Метод GetFunctionTailcall3Info](icorprofilerinfo3-getfunctiontailcall3info-method.md)
#### [Метод GetModuleInfo2](icorprofilerinfo3-getmoduleinfo2-method.md)
#### [Метод GetRuntimeInformation](icorprofilerinfo3-getruntimeinformation-method.md)
#### [Метод GetStringLayout2](icorprofilerinfo3-getstringlayout2-method.md)
#### [Метод GetThreadStaticAddress2](icorprofilerinfo3-getthreadstaticaddress2-method.md)
#### [Метод RequestProfilerDetach](icorprofilerinfo3-requestprofilerdetach-method.md)
#### [Метод SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
#### [Метод SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
#### [Метод SetFunctionIDMapper2](icorprofilerinfo3-setfunctionidmapper2-method.md)
### [Интерфейс ICorProfilerInfo4](icorprofilerinfo4-interface.md)
#### [Метод EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md)
#### [Метод EnumThreads](icorprofilerinfo4-enumthreads-method.md)
#### [Метод GetCodeInfo3](icorprofilerinfo4-getcodeinfo3-method.md)
#### [Метод GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md)
#### [Метод GetILToNativeMapping2](icorprofilerinfo4-getiltonativemapping2-method.md)
#### [Метод GetObjectSize2](icorprofilerinfo4-getobjectsize2-method.md)
#### [Метод GetReJITIDs](icorprofilerinfo4-getrejitids-method.md)
#### [Метод InitializeCurrentThread](icorprofilerinfo4-initializecurrentthread-method.md)
#### [Метод RequestReJIT](icorprofilerinfo4-requestrejit-method.md)
#### [Метод RequestRevert](icorprofilerinfo4-requestrevert-method.md)
### [Интерфейс ICorProfilerInfo5](icorprofilerinfo5-interface.md)
#### [Метод GetEventMask2](icorprofilerinfo5-geteventmask2-method.md)
#### [Метод SetEventMask2](icorprofilerinfo5-seteventmask2-method.md)
### [Интерфейс ICorProfilerInfo6](icorprofilerinfo6-interface.md)
#### [Метод ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod](icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)
### [Интерфейс ICorProfilerInfo7](icorprofilerinfo7-interface.md)
#### [Метод ApplyMetaData](icorprofilerinfo7-applymetadata-method.md)
#### [Метод GetInMemorySymbolsLength](icorprofilerinfo7-getinmemorysymbolslength-method.md)
#### [ReadInMemorySymbols](icorprofilerinfo7-readinmemorysymbols.md)
### [Интерфейс ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md)
#### [Метод Clone](icorprofilermoduleenum-clone-method.md)
#### [Метод GetCount](icorprofilermoduleenum-getcount-method.md)
#### [Метод Next](icorprofilermoduleenum-next-method.md)
#### [Метод Reset](icorprofilermoduleenum-reset-method.md)
#### [Метод Skip](icorprofilermoduleenum-skip-method.md)
### [Интерфейс ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md)
#### [Метод Clone](icorprofilerobjectenum-clone-method.md)
#### [Метод GetCount](icorprofilerobjectenum-getcount-method.md)
#### [Метод Next](icorprofilerobjectenum-next-method.md)
#### [Метод Reset](icorprofilerobjectenum-reset-method.md)
#### [Метод Skip](icorprofilerobjectenum-skip-method.md)
### [Интерфейс ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md)
#### [Метод Clone](icorprofilerthreadenum-clone-method.md)
#### [Метод GetCount](icorprofilerthreadenum-getcount-method.md)
#### [Метод Next](icorprofilerthreadenum-next-method.md)
#### [Метод Reset](icorprofilerthreadenum-reset-method.md)
#### [Метод Skip](icorprofilerthreadenum-skip-method.md)
### [Интерфейс IMethodMalloc](imethodmalloc-interface.md)
#### [Метод Alloc](imethodmalloc-alloc-method.md)
## [Глобальные статические функции профилирования](profiling-global-static-functions.md)
### [Функция FunctionEnter](functionenter-function.md)
### [Функция FunctionEnter2](functionenter2-function.md)
### [Функция FunctionEnter3](functionenter3-function.md)
### [Функция FunctionEnter3WithInfo](functionenter3withinfo-function.md)
### [Функция FunctionIDMapper](functionidmapper-function.md)
### [Функция FunctionIDMapper2](functionidmapper2-function.md)
### [Функция FunctionLeave](functionleave-function.md)
### [Функция FunctionLeave2](functionleave2-function.md)
### [Функция FunctionLeave3](functionleave3-function.md)
### [Функция FunctionLeave3WithInfo](functionleave3withinfo-function.md)
### [Функция FunctionTailcall](functiontailcall-function.md)
### [Функция FunctionTailcall2](functiontailcall2-function.md)
### [Функция FunctionTailcall3](functiontailcall3-function.md)
### [Функция FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)
### [Функция StackSnapshotCallback](stacksnapshotcallback-function.md)
## [Перечисления профилирования](profiling-enumerations.md)
### [Перечисление COR_PRF_CLAUSE_TYPE](cor-prf-clause-type-enumeration.md)
### [Перечисление COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md)
### [Перечисление COR_PRF_FINALIZER_FLAGS](cor-prf-finalizer-flags-enumeration.md)
### [Перечисление COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md)
### [Перечисление COR_PRF_GC_REASON](cor-prf-gc-reason-enumeration.md)
### [Перечисление COR_PRF_GC_ROOT_FLAGS](cor-prf-gc-root-flags-enumeration.md)
### [Перечисление COR_PRF_GC_ROOT_KIND](cor-prf-gc-root-kind-enumeration.md)
### [Перечисление COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md)
### [Перечисление COR_PRF_JIT_CACHE](cor-prf-jit-cache-enumeration.md)
### [Перечисление COR_PRF_MISC](cor-prf-misc-enumeration.md)
### [Перечисление COR_PRF_MODULE_FLAGS](cor-prf-module-flags-enumeration.md)
### [Перечисление COR_PRF_MONITOR](cor-prf-monitor-enumeration.md)
### [Перечисление COR_PRF_RUNTIME_TYPE](cor-prf-runtime-type-enumeration.md)
### [Перечисление COR_PRF_SNAPSHOT_INFO](cor-prf-snapshot-info-enumeration.md)
### [Перечисление COR_PRF_STATIC_TYPE](cor-prf-static-type-enumeration.md)
### [Перечисление COR_PRF_SUSPEND_REASON](cor-prf-suspend-reason-enumeration.md)
### [Перечисление COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md)
## [Структуры профилирования](profiling-structures.md)
### [Структура COR_PRF_ASSEMBLY_REFERENCE_INFO](cor-prf-assembly-reference-info-structure.md)
### [Структура COR_PRF_CODE_INFO](cor-prf-code-info-structure.md)
### [Структура COR_PRF_EX_CLAUSE_INFO](cor-prf-ex-clause-info-structure.md)
### [Структура COR_PRF_FUNCTION](cor-prf-function-structure.md)
### [Структура COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md)
### [Структура COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md)
### [Структура COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md)
