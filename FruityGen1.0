import bpy
import random

#Code created by Amir B Jahanbin
#Visit http://jahanbin.net/ for more!
#Follow @abjahanbin

#clear all 
 
bpy.ops.object.select_all(action='SELECT')
bpy.ops.object.delete(use_global=False)

#create Mball

rT = random.uniform(0.5,5.5)
z = random.uniform(rT,rT+1.0)
x = random. uniform(0.0,rT/2)
y = random. uniform(0.0,rT/2)
xB = random. uniform(0.0,rT/4)
yB = random. uniform(0.0,rT/4)
s = random.uniform(1.0,1.5)
b = random.uniform(-3.0,3.0)
b2 = random.uniform(-1.0,1.0)
c = random.randint(4,8)

leafR1 = random.uniform(0.0,0.8)
leafR2 = random.uniform(-0.4,0.4)
leafR3 = random.uniform(0.0,6.0)
leafW = random.uniform(0.05,0.2)
leafC = random.randint(5,12)

spinX = random.uniform(-0.7,0.7)
spinY = random.uniform(-0.7,0.7)
spinZ = random.uniform(-0.7,0.7)

#lemon
if rT < 1.0:
    
    #body

    bpy.ops.object.metaball_add(type='BALL', radius=rT, location=(0, 0, 0))
    
    bpy.ops.object.metaball_add(type='BALL', radius=rT/3, location=(0, 0, rT))
    bpy.ops.object.metaball_add(type='BALL', radius=rT/4, location=(0, 0, -rT))
    
    bpy.context.object.data.render_resolution = 0.3
    bpy.context.object.data.threshold = 0.5
    bpy.context.object.data.resolution = 0.3
    
    #leaf
    
    bpy.ops.mesh.primitive_plane_add(size=2.0, enter_editmode=False, location=(0, 0, (rT*1.4)))
    bpy.ops.transform.resize(value=(leafW, 0.1, .5))
    bpy.context.object.rotation_euler[0] = leafR1
    bpy.context.object.rotation_euler[1] = leafR2
    bpy.context.object.rotation_euler[2] = leafR3
    
    bpy.ops.object.modifier_add(type='ARRAY')
    bpy.context.object.modifiers["Array"].relative_offset_displace[0] = 0.0
    bpy.context.object.modifiers["Array"].relative_offset_displace[1] = 0.5
    bpy.context.object.modifiers["Array"].relative_offset_displace[2] = 0.0
    bpy.context.object.modifiers["Array"].count = leafC-1
    
    bpy.ops.object.modifier_add(type='SIMPLE_DEFORM')
    bpy.context.object.modifiers["SimpleDeform"].deform_method = 'TAPER'
    bpy.context.object.modifiers["SimpleDeform"].deform_axis = 'Y'
    bpy.context.object.modifiers["SimpleDeform"].factor = -1.07
    
    bpy.ops.object.modifier_add(type='SIMPLE_DEFORM')
    bpy.context.object.modifiers["SimpleDeform.001"].deform_method = 'TAPER'
    bpy.context.object.modifiers["SimpleDeform.001"].deform_axis = 'Y'
    bpy.context.object.modifiers["SimpleDeform.001"].factor = 10.0
    
    #spin
    bpy.ops.object.select_all(action='SELECT')
    bpy.ops.transform.rotate(value=spinX, orient_axis='X')
    bpy.ops.transform.rotate(value=spinY, orient_axis='Y')
    bpy.ops.transform.rotate(value=spinZ, orient_axis='Z')
    
    #bake
    bpy.context.scene.objects["Mball"].select_set(True)
    bpy.ops.object.convert(target='MESH')


#pear
elif rT < 2.0:
    
    #body
    bpy.ops.object.metaball_add(type='BALL', radius=rT, location=(0, 0, 0))
    bpy.ops.object.metaball_add(type='BALL', radius=(rT/2), location=(x, y, z))
    bpy.ops.object.metaball_add(type='BALL', radius=(rT/4), location=(xB, yB, -rT))
    
    bpy.context.object.data.render_resolution = 0.5
    bpy.context.object.data.threshold = 0.5
    bpy.context.object.data.resolution = 0.5
    
    #stem
    bpy.ops.mesh.primitive_cylinder_add(vertices=12, radius=0.1, depth=0.2, location=(x*1.2, y*1.2, (rT+(rT/1.5))))

    bpy.ops.object.modifier_add(type='ARRAY')
    bpy.context.object.modifiers["Array"].relative_offset_displace[0] = 0.0
    bpy.context.object.modifiers["Array"].relative_offset_displace[1] = 0.0
    bpy.context.object.modifiers["Array"].relative_offset_displace[2] = 1.0
    bpy.context.object.modifiers["Array"].count = c

    bpy.ops.object.modifier_add(type='SIMPLE_DEFORM')
    bpy.context.object.modifiers["SimpleDeform"].deform_method = 'BEND'
    bpy.context.object.modifiers["SimpleDeform"].angle = b
    
    #leaf
    bpy.ops.mesh.primitive_plane_add(size=2.5, enter_editmode=False, location=(x*1.5, y*1.5, (rT*1.9)))
    bpy.ops.transform.resize(value=(leafW, 0.1, 1))
    bpy.context.object.rotation_euler[0] = leafR1
    bpy.context.object.rotation_euler[1] = leafR2
    bpy.context.object.rotation_euler[2] = leafR3
    
    bpy.ops.object.modifier_add(type='ARRAY')
    bpy.context.object.modifiers["Array"].relative_offset_displace[0] = 0.0
    bpy.context.object.modifiers["Array"].relative_offset_displace[1] = 1.0
    bpy.context.object.modifiers["Array"].relative_offset_displace[2] = 0.0
    bpy.context.object.modifiers["Array"].count = leafC
    
    bpy.ops.object.modifier_add(type='SIMPLE_DEFORM')
    bpy.context.object.modifiers["SimpleDeform"].deform_method = 'TAPER'
    bpy.context.object.modifiers["SimpleDeform"].deform_axis = 'Y'
    bpy.context.object.modifiers["SimpleDeform"].factor = -1.07
    
    bpy.ops.object.modifier_add(type='SIMPLE_DEFORM')
    bpy.context.object.modifiers["SimpleDeform.001"].deform_method = 'TAPER'
    bpy.context.object.modifiers["SimpleDeform.001"].deform_axis = 'Y'
    bpy.context.object.modifiers["SimpleDeform.001"].factor = 10.0
    
    #bake
    bpy.context.scene.objects["Mball"].select_set(True)
    bpy.ops.object.convert(target='MESH')
    
#orange
elif rT < 3.0:
    
    #body
    bpy.ops.object.metaball_add(type='BALL', radius=rT, location=(0, 0, 0))
    bpy.ops.object.metaball_add(type='BALL', radius=rT/5, location=(0, 0, -(rT+(rT/5))))
    bpy.context.object.data.render_resolution = 1.1
    bpy.context.object.data.resolution = 1.1
    bpy.context.object.data.threshold = 0.5
    
    #stembase
    bpy.ops.mesh.primitive_plane_add(size=rT/3.0, enter_editmode=False, location=(0, 0, rT+(rT/5)))
    bpy.ops.mesh.primitive_plane_add(size=rT/3.0, enter_editmode=False, location=(0, 0, rT+(rT/5)+.001))
    bpy.context.object.rotation_euler[2] = 0.785398
    
    #stem
    bpy.ops.mesh.primitive_cylinder_add(vertices=12, radius=0.2, depth=0.2, location=(0, 0, (rT+(rT/5))))

    bpy.ops.object.modifier_add(type='ARRAY')
    bpy.context.object.modifiers["Array"].relative_offset_displace[0] = 0.0
    bpy.context.object.modifiers["Array"].relative_offset_displace[1] = 0.0
    bpy.context.object.modifiers["Array"].relative_offset_displace[2] = 1.0
    bpy.context.object.modifiers["Array"].count = c-2.0

    bpy.ops.object.modifier_add(type='SIMPLE_DEFORM')
    bpy.context.object.modifiers["SimpleDeform"].deform_method = 'BEND'
    bpy.context.object.modifiers["SimpleDeform"].angle = b2
    
    #leaf
    bpy.ops.mesh.primitive_plane_add(size=3.0, location=(0, 0, rT+(rT/4)))
    bpy.ops.transform.resize(value=(leafW, 0.1, 1))
    bpy.context.object.rotation_euler[0] = leafR1
    bpy.context.object.rotation_euler[1] = leafR2
    bpy.context.object.rotation_euler[2] = leafR3
    
    bpy.ops.object.modifier_add(type='ARRAY')
    bpy.context.object.modifiers["Array"].relative_offset_displace[0] = 0.0
    bpy.context.object.modifiers["Array"].relative_offset_displace[1] = 1.0
    bpy.context.object.modifiers["Array"].relative_offset_displace[2] = 0.0
    bpy.context.object.modifiers["Array"].count = leafC
    
    bpy.ops.object.modifier_add(type='SIMPLE_DEFORM')
    bpy.context.object.modifiers["SimpleDeform"].deform_method = 'TAPER'
    bpy.context.object.modifiers["SimpleDeform"].deform_axis = 'Y'
    bpy.context.object.modifiers["SimpleDeform"].factor = -1.07
    
    bpy.ops.object.modifier_add(type='SIMPLE_DEFORM')
    bpy.context.object.modifiers["SimpleDeform.001"].deform_method = 'TAPER'
    bpy.context.object.modifiers["SimpleDeform.001"].deform_axis = 'Y'
    bpy.context.object.modifiers["SimpleDeform.001"].factor = 10.0
    
    #spin
    bpy.ops.object.select_all(action='SELECT')
    bpy.ops.transform.rotate(value=spinX, orient_axis='X')
    bpy.ops.transform.rotate(value=spinY, orient_axis='Y')
    bpy.ops.transform.rotate(value=spinZ, orient_axis='Z')
    
    #bake
    bpy.context.scene.objects["Mball"].select_set(True)
    bpy.ops.object.convert(target='MESH')
    
#Banana
elif rT < 4.5:
    
    #body
    hB = random.uniform(8,12)
    bB = random.uniform(0.7,2.5)
    rB = random.uniform(1.0,1.5)
    dB = random.uniform(0.09,0.22)
    
    bpy.ops.mesh.primitive_cylinder_add(vertices=12, radius=rB, depth=hB, location=(0, 0, 0))
    bpy.ops.object.modifier_add(type='SUBSURF')
    bpy.context.object.modifiers["Subdivision"].levels = 2
    bpy.context.object.modifiers["Subdivision"].quality = 2
    bpy.ops.object.modifier_add(type='SIMPLE_DEFORM')
    bpy.context.object.modifiers["SimpleDeform"].deform_method = 'BEND'
    bpy.context.object.modifiers["SimpleDeform"].angle = bB
    bpy.ops.object.modifier_add(type='DECIMATE')
    bpy.context.object.modifiers["Decimate"].ratio = dB
    
    #stem
    bpy.ops.object.empty_add(type='PLAIN_AXES', location=(0, 0, 0))
    bpy.ops.mesh.primitive_cylinder_add(vertices=6, radius=rB/5, depth=hB/5, location=(0, 0, hB/2.2))
    bpy.ops.object.modifier_add(type='SIMPLE_DEFORM')
    bpy.context.object.modifiers["SimpleDeform"].deform_method = 'BEND'
    bpy.context.object.modifiers["SimpleDeform"].origin = bpy.data.objects["Empty"]
    bpy.context.object.modifiers["SimpleDeform"].angle = bB/5
    
    bpy.ops.mesh.primitive_cylinder_add(vertices=6, radius=rB/5, depth=hB/5, location=(0, 0, -hB/2.2))
    bpy.ops.object.modifier_add(type='SIMPLE_DEFORM')
    bpy.context.object.modifiers["SimpleDeform"].deform_method = 'BEND'
    bpy.context.object.modifiers["SimpleDeform"].origin = bpy.data.objects["Empty"]
    bpy.context.object.modifiers["SimpleDeform"].angle = bB/5
    
    bpy.ops.object.select_all(action='SELECT')
    bpy.ops.transform.rotate(value=spinX, orient_axis='X')
    bpy.ops.transform.rotate(value=spinY, orient_axis='Y')
    bpy.ops.transform.rotate(value=spinZ, orient_axis='Z')

#spikey
elif rT < 5.5:
    
    #body

    bpy.ops.object.metaball_add(type='BALL', radius=rT/1.5, location=(0, 0, 0))
    bpy.ops.object.metaball_add(type='BALL', radius=rT/2.5, location=(0, 0, rT/1.2))    
    
    bpy.context.object.data.render_resolution = 1.5
    bpy.context.object.data.threshold = 0.5
    bpy.context.object.data.resolution = 1.5
    
    #stem
    bpy.ops.mesh.primitive_cylinder_add(vertices=12, radius=0.4, depth=0.2, location=(0, 0, (rT+1.0)))

    bpy.ops.object.modifier_add(type='ARRAY')
    bpy.context.object.modifiers["Array"].relative_offset_displace[0] = 0.0
    bpy.context.object.modifiers["Array"].relative_offset_displace[1] = 0.0
    bpy.context.object.modifiers["Array"].relative_offset_displace[2] = 1.0
    bpy.context.object.modifiers["Array"].count = c

    bpy.ops.object.modifier_add(type='SIMPLE_DEFORM')
    bpy.context.object.modifiers["SimpleDeform"].deform_method = 'BEND'
    bpy.context.object.modifiers["SimpleDeform"].angle = b
    
    #spin
    bpy.ops.object.select_all(action='SELECT')
    bpy.ops.transform.rotate(value=spinX, orient_axis='X')
    bpy.ops.transform.rotate(value=spinY, orient_axis='Y')
    bpy.ops.transform.rotate(value=spinZ, orient_axis='Z')
    
    #bake
    bpy.context.scene.objects["Mball"].select_set(True)
    bpy.ops.object.convert(target='MESH')

bpy.ops.object.select_all(action='DESELECT')
