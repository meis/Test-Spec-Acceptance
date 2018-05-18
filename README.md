# NAME

Test::Spec::Acceptance - Write tests in a declarative specification style

# SYNOPSIS

    use Test::Spec::Acceptance;    # Also loads Test::Spec

    Feature "Test::Spec::Acceptance tests module" => sub {
        Scenario "Usage example" => sub {
            my ($number, $accumulated);

            Given "a relevant number" => sub {
                $number = 42;
            };
            When "we add 0 to it" => sub {
                $accumulated = $number + 0
            };
            When "we add 0 again" => sub {
                $accumulated = $number + 0
            };
            Then "it does not change it's value" => sub {
                is($accumulated, 42);
            };
        };
    };

    runtests;

# DESCRIPTION

This is a shameless wrapper around [Test::Spec](https://metacpan.org/pod/Test::Spec). It does everything [Test::Spec](https://metacpan.org/pod/Test::Spec) does, plus it aliases some exported names to make acceptance-style tests more legible.

I understand this is a bit silly and this is not how `Test::Spec` is intended to work (using tests without any assertion) but I just think it's nice and more readable. I've had good experiencies expressing some tests this way.

The new keywords are:

- Feature

    An alias for `describe()`.

- Scenario

    An alias for `describe()`.

- Given

    An alias for `it()`.

- When

    An alias for `it()`.

- Then

    An alias for `it()`.

- And

    An alias for `it()`.

# SEE ALSO

Please, see the excellent [Test::Spec](https://metacpan.org/pod/Test::Spec).
