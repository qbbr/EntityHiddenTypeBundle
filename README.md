# EntityHiddenTypeBundle

## Installation

### Step 1: Download the Bundle

```bash
$ composer require qbbr/entity-hidden-type-bundle
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

class MyType extends AbstractType
{
    public function buildForm(FormBuilderInterface $builder, array $options)
    {
        $builder
            ->add('parent', 'entity_hidden', [
                'class' => 'AppBundle\Entity\MyEntity',
            ]);
    }

    public function getName()
    {
        return 'my';
    }
}
```
