# Thinking in React

## Step 1: Break The UI Into A Component Hierarchy

* mockup UI with component boxes
* [single responsibility principle](https://en.wikipedia.org/wiki/Single-responsibility_principle)
* UI & Data Model information architecture mapped with symmetry 
* outline parent-child hierarchy

## Step 2: Build A Static Version in React

* render data model with UI without interactivity (state)
* parents pass props to children
* top component accepts data model as prop

## Step 3: Identify The Minimal (but complete) Representation Of UI State

* determine minimal state needed for [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself)
* compute everything else on-demand
* is each piece of data (not components)
  * passed in from parent via props? not state
  * never changed? not state
  * computable from other props or state? not state

## Step 4: Identify Where Your State Should Live

* determine which component(s) should own state
* for each piece of state (not components)
  * which component(s) render any part of it?
      * which common component is above each?
          * that’s the owner
              * or another component higher
                  * or even a new component

## Step 5: Add Inverse Data Flow

* components should only update their own state
* parents pass callbacks to children to update parent’s state

---

### Acronym Reminder for Five Steps

**C** omponents  
**S** tatic  
**S** tate  
**H** ome  
**T** ransfer

---

### Summary

- Code is read far more than it’s written
- Goal is modular and explicit code for DRY
