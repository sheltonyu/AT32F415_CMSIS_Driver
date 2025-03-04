from building import *
import os

cwd = GetCurrentDir()

path = [cwd]
src = [os.path.join(cwd, 'system_at32f415.c')]

if rtconfig.PLATFORM in ['gcc', 'llvm-arm']:
    src += [os.path.join(cwd, 'startup', 'gcc', 'startup_at32f415.s')]
elif rtconfig.PLATFORM in ['armcc', 'armclang']:
    src += [os.path.join(cwd, 'startup', 'mdk', 'startup_at32f415.s')]
elif rtconfig.PLATFORM in ['iccarm']:
    src += [os.path.join(cwd, 'startup', 'iar', 'startup_at32f415.s')]

group = DefineGroup('cmsis', src, depend = ['PKG_USING_AT32F415_CMSIS_DRIVER'], CPPPATH = path)

Return('group')
