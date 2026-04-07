# Cómo subir el repositorio a GitHub — Iran Conflict Model (ICM)

## ¿Por qué necesitas hacer esto?

Ahora mismo el repositorio solo existe en tu PC. Para que GitHub Actions funcione y para que otros puedan replicar el experimento, necesitas subirlo a github.com. Es un proceso de una sola vez.

---

## Lo que necesitas

- Una cuenta en github.com (gratuita)
- Git instalado en tu PC (ya lo tienes — lo usaste para los commits)
- 10 minutos

---

## Paso 1 — Crea el repositorio en github.com

1. Ve a github.com e inicia sesión
2. Haz click en el botón verde **"New"** o en el símbolo **"+"** arriba a la derecha
3. Llena el formulario así:

```
Repository name:  iran-conflict-model
Description:      Sistema de análisis del conflicto 
                  EEUU-Israel-Irán mediante inferencia causal
Visibility:       Public (para que sea replicable por cualquiera)
                  o Private (si prefieres acceso controlado)

⚠️ MUY IMPORTANTE: NO marques ninguna de estas opciones:
   □ Add a README file
   □ Add .gitignore
   □ Choose a license
   
   Si las marcas, GitHub crea commits propios que 
   entran en conflicto con los tuyos.
```

4. Haz click en **"Create repository"**

---

## Paso 2 — Conecta tu repositorio local con GitHub

GitHub te mostrará una página con instrucciones. Busca la sección que dice **"…or push an existing repository from the command line"** y ejecuta esos comandos en tu terminal.

Son exactamente estos (reemplaza `tu-usuario` con tu nombre de usuario de GitHub):

```bash
git remote add origin https://github.com/tu-usuario/iran-conflict-model.git
git branch -M main
git push -u origin main
```

---

## Paso 3 — Verifica que todo subió correctamente

1. Ve a `https://github.com/tu-usuario/iran-conflict-model`
2. Debes ver todos tus archivos y carpetas
3. Verifica que aparecen los tres commits:

```
v0.1.1 — evidencia experimental sesión 01
v0.1.0 — arquitectura inicial del modelo
Initial commit
```

---

## Paso 4 — Configura el acceso para futuros pushes

Para no tener que ingresar tu contraseña cada vez que hagas push, configura un token de acceso personal:

1. En github.com ve a: **Settings → Developer settings → Personal access tokens → Tokens (classic)**
2. Click en **"Generate new token (classic)"**
3. Dale un nombre: `iran-conflict-model`
4. Selecciona el permiso: **repo** (marca la casilla principal)
5. Click en **"Generate token"**
6. **Copia el token inmediatamente** — GitHub no te lo mostrará de nuevo

Cuando Git te pida contraseña en el terminal, usa ese token en lugar de tu contraseña.

---

## Cómo se verá tu repositorio en github.com

```
iran-conflict-model/
├── README.md          ← descripción del proyecto
├── CHANGELOG.md       ← historial de versiones
├── docs/              ← diseño experimental y guías
├── simulaciones/      ← registro de sesiones
├── prompts/           ← evidencia experimental
└── datos/             ← datos crudos del experimento
```

---

## Comandos de uso diario

Después de cada sesión, estos son los únicos comandos que necesitas:

```bash
git add .
git commit -m "sesión [N] — [FECHA] — [TIPO]"
git push
```

---

## Si algo sale mal

**Error: "remote origin already exists"**
```bash
git remote remove origin
git remote add origin https://github.com/tu-usuario/iran-conflict-model.git
```

**Error: "failed to push — non-fast-forward"**
```bash
git pull origin main
git push origin main
```

**No sabes si Git está instalado**
```bash
git --version
```
Si ves un número de versión, está instalado. Si no, descárgalo de git-scm.com.

---

*Guía de configuración GitHub v0.1.3*
