
```code
erdiagram EmpresaInicial
notation=crowsfoot
```

---
### Entidades
####  Entidad Empleado
```code
entity Empleado {
dni key
nombre
apellido_1
apellido_2
fecha_nacimiento
direccion
sexo
sueldo
}
```
#### Entidad Departamento
```code
entity Departamento {
numero_departamento key
nombre unique
ubicaciones
}
```
#### Entidad Proyecto
```code
entity Proyecto {
numero_proyecto key
nombre unique
ubicacion
}
```
#### Entidad Familiar
```code
entity Familiar {
nombre key
sexo
fecha_nacimiento
relacion
}
```

---
### Relaciones
#### Relación trabaja_para
```code
relationship trabaja_para {
Empleado[1..N] -> Departamento[1..1]
}
```
#### Relación dirige
```code
relationship dirige {
Empleado[1..1] -> Departamento[0..1]
fecha_ingreso_director
}
```
#### Relación trabaja_en
```code
relationship trabaja_en {
Empleado[1..N] -> Proyecto[0..N]
horas
}
```
#### Relación controla
```code
relationship controla {
Proyecto[0..N] -> Departamento[1..1]
}
```
#### Relación supervisa
```code
relationship supervisa {
Empleado[0..1 | "Supervisor" ] -> Empleado[0..N | "Supervisado"]
}
```
#### Relación familiar_de 
```code
relationship familiar_de {
Familiar[0..N] -> Empleado[1..1]
}
```

---
### Diagrama resultante en notación crow's foot

![](../../imgs/BD%20-%20BigER%20Empresa%20version%20inicial%20incorrecta.png)
