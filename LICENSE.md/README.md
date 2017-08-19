# Python
A Python Demo
# -*- coding: utf-8 -*-

import math

def quadratic(a, b, c):
    key={'RootType':None,'Root1':None,'Root2':None}
    d = b * b - 4 * a * c
    if d == 0:
        key['RootType'] = 0
        key['Root1'] = key['Root2'] = -b / 2 * a
        return key
    elif d > 0:
        key['RootType']=1
        key['Root1'] = (-b + math.sqrt(d)) / 2*a
        key['Root2'] = (-b - math.sqrt(d)) / 2*a
        return key
    else:
        key['RootType'] = 2
        key['Root1'] = key['Root2'] = None
        return key
    
print('ax2+bx+c=0')
ValueA = input('please input a')
ValueB = input('please input b')
ValueC = input('please input c')

A = float(ValueA)
B = float(ValueB)
C = float(ValueC)
print('%dx2+%dx+%d=0\n'%( A, B, C))
Root = quadratic(A, B, C)
if Root['RootType'] == 0:
    print('one ture root:x1=x2=%.3f\n'%Root['Root1'])
if Root['RootType'] == 1:
    print('two ture roots:x1=%.3f,x2=%.3f\n'%(Root['Root1'],Root['Root2']))
if Root['RootType'] == 2:
    print('no ture root')
