 <!-- style Usuario fill:#efe;
    style Decano fill:#eef;
    style Comisi�n fill:#fef; -->

## Proceso de comisi�n disciplinaria
```mermaid
graph TD
    denuncia(Emite denuncia):::auto-->proceeds{"�Procede?"}-->sip((S�))-->assign(Asigna comisi�n disciplinaria):::auto-->info(Recopila informaci�n del caso):::auto-->conc(Emite conclusiones):::auto-->ac{"�Se aceptan?"}-->sic((S�))-->emit_case_resolution(Emite resoluci�n de caso):::auto-->notif(Notifica a los infractores):::auto-->fin((fin))

    proceeds-->nop((No))-->Sobreseimiento:::auto
    ac-->noc((No))-->reunion(Reuni�n y correcci�n)-->emit_case_resolution

    classDef auto fill:yellow,color:black;
    class denuncia auto;
   

    subgraph Usuario
    denuncia
    end
    subgraph Decano
    proceeds & sip & nop & assign & Sobreseimiento & ac & sic & noc & emit_case_resolution & notif & reunion & fin
    end
    subgraph Comisi�n
    info & conc
    end
```

```mermaid
pie showData
    title Resultado de las pruebas de sistema
    "Satisfactorias" : 24
    "No satisfactorias" : 4
```
