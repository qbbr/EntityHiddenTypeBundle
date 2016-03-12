# EntityHiddenTypeBundle

[![Latest Stable Version](https://poser.pugx.org/qbbr/entity-hidden-type-bundle/v/stable)](https://packagist.org/packages/qbbr/entity-hidden-type-bundle)
[![Total Downloads](https://poser.pugx.org/qbbr/entity-hidden-type-bundle/downloads)](https://packagist.org/packages/qbbr/entity-hidden-type-bundle)
[![License](https://poser.pugx.org/qbbr/entity-hidden-type-bundle/license)](https://packagist.org/packages/qbbr/entity-hidden-type-bundle)

## Installation

### Step 1: Download the Bundle

### Symfony >= 2.8

```bash
$ composer require qbbr/entity-hidden-type-bundle
```

### Symfony < 2.8

```bash
$ composer require qbbr/entity-hidden-type-bundle 1.*
```

### Step 2: Enable the Bundle

```php
<?php
// app/AppKernel.php

// ...
class AppKernel extends Kernel
{
    public function registerBundles()
    {
        $bundles = array(
            // ...

            new Qbbr\EntityHiddenTypeBundle\EntityHiddenTypeBundle(),
        );

        // ...
    }

    // ...
}
```

## Usage

```php
<?php
// src/AppBundle/Form/Type/MyType.php
namespace AppBundle\Form\Type;

use Symfony\Component\Form\AbstractType;
use Symfony\Component\Form\FormBuilderInterface;
// for Symfony < 2.8 rm use type
use Qbbr\EntityHiddenTypeBundle\Form\Type\EntityHiddenType;

class MyType extends AbstractType
{
    public function buildForm(FormBuilderInterface $builder, array $options)
    {
        $builder
            // for < 2.8 use 'entity_hidden'
            ->add('parent', EntityHiddenType::class, [
                'class' => 'AppBundle\Entity\MyEntity',
            ]);
    }

    // for < 2.8 use getName()
    public function getBlockPrefix()
    {
        return 'my';
    }
}
```
