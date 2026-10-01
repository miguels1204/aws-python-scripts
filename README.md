# aws-python-scripts

Small Python tools for auditing and cleaning up AWS accounts, written with boto3 and tested with pytest and moto. A learning project built in the open: I write the code myself and add tests as I go.

> **Status: in progress.** Scripts land one at a time, and the roadmap below gets ticked as they do.
> Built on my personal AWS account with read-only credentials. No employer code, names or data.

## Planned scripts

| Script | What it will do |
| --- | --- |
| `find_orphaned_resources` | List unattached EBS volumes and unused Elastic IPs in a region and export a CSV report |
| `audit_s3_buckets` | Flag buckets without encryption or with public access |
| `check_route53_records` | Flag DNS records that point to targets that no longer exist |

## Roadmap

- [ ] Project skeleton, `requirements.txt` and test setup
- [ ] `find_orphaned_resources` with tests
- [ ] `audit_s3_buckets` with tests
- [ ] `check_route53_records` with tests
- [ ] Command line interface shared by all scripts
- [ ] GitHub Actions workflow that runs the tests on every push

## Layout

```
src/        the scripts
tests/      pytest tests using moto to mock AWS
requirements.txt
```

## How to run

Instructions will be added with the first script. The plan is:

```
pip install -r requirements.txt
pytest
python -m src.find_orphaned_resources --region eu-west-1
```

Tests run against moto, so they need no AWS credentials.

## Safety

- Scripts only read; they never delete or modify resources.
- No credentials are stored in this repository, and secret scanning is enabled.
- Use a read-only IAM user on a personal account.

## What I'm practising

Python fundamentals, error handling, working with the AWS API through boto3, testing with pytest and moto, and writing small tools others can run.

## License

MIT
