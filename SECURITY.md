README.mdstaticText = {
  // ...
  direction: (status) => status,
  // ...
}direction: {
  name: 'direction',
  permission: 'read_compass',
  supportedMakes: ['TESLA'],
  requestType: 'GET',
  componentType: 'VehicleProperty',
  text: 'Direction',
}direction: {
  endpoint: (make) => `/${make.toLowerCase()}/compass`,
  supportedMakes: ['TESLA'],
  process: (batchResponse, make) => {
    try {
      if (make === 'TESLA') {
        return batchResponse.teslaCompass().direction;
      }
      throw new Error ('Unsupported make')
    } catch (err) {
      return handleError(err);
    }
  },
}  direction: {
    endpoint: (make) => `/${make.toLowerCase()}/compass`,
    supportedMakes: ['TESLA'],
    process: (batchResponse, make) => {
      try {
        if (make === 'TESLA') {
          return batchResponse.teslaCompass().direction;
        }
        throw new Error ('Unsupported make')
      } catch (err) {
        return handleError(err);
      }
    },
  }# Security Policy

## Supported Versions

Use this section to tell people about which versions of your project are
currently being supported with security updates.

| Version | Supported          |
| ------- | ------------------ |
| 5.1.x   | :white_check_mark: |
| 5.0.x   | :x:                |
| 4.0.x   | :white_check_mark: |
| < 4.0   | :x:                |

## Reporting a Vulnerability

Use this section to tell people how to report a vulnerability.

Tell them where to go, how often they can expect to get an update on a
reported vulnerability, what to expect if the vulnerability is accepted or
declined, etc.
