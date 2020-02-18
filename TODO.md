vpc.yml
- region is hardcoded
- use conditional logic to allow a parameter to determine how many AZs to use
  - parm: NumberOfAvailabilityZones (numeric)
  - Conditions:
      CreateSubnet2:
        Fn:Or:
          - Fn::Equals:
            - Ref: NumberOfAvailabilityZones
            - 2
          - Fn::Equals:
            - Ref: NumberOfAvailabilityZones
            - 3
          - Fn::Equals:
            - Ref: NumberOfAvailabilityZones
            - 4
          - Fn::Equals:
            - Ref: NumberOfAvailabilityZones
            - 5
          - Fn::Equals:
            - Ref: NumberOfAvailabilityZones
            - 6
      CreateSubnet3:
        Fn:Or:
          - Fn::Equals:
            - Ref: NumberOfAvailabilityZones
            - 3
          - Fn::Equals:
            - Ref: NumberOfAvailabilityZones
            - 4
          - Fn::Equals:
            - Ref: NumberOfAvailabilityZones
            - 5
          - Fn::Equals:
            - Ref: NumberOfAvailabilityZones
            - 6
      CreateSubnet4: (etc)
